# ESX

Die ESX-Version ist nur mit dem verbreiteten ESX-Legacy framework kompatibel.  
[Download hier](download)  

### Installation
Das Skript kann ganz einfach in den `resources` Ordner entpackt werden.  
Denke daran, es in der server.cfg einzutragen. 


### Config
#### Erklärung

##### Config.Enable
Soll das Script aktiviert werden und Spielerpositionen an die LiveMap gesendet werden?
- Ja `true`
- Nein `false`


##### Config.DebugMode
Soll der Debugmode aktiviert werden? Dieser Modus gibt Diagnoseinformationen in der Serverkonsole aus.  
Für den Produktiv einsatz nicht geeignet.
- Ja `true`
- Nein `false`


##### Config.PrivateKey
Dieser Schlüssel identifiziert das Script bei CopNet. Du erhälst ihn im vCAD-System unter Einstellungen -> Livemap einstellungen  

!> **Wichtig!** Halte diesen Schlüssel geheim, um Manipulation zu verhindern. Solltest du den Schlüssel verlieren, kannst du ihn in den Einstellungen zurücksetzen

Der Text muss zwischen zwei Anführungszeichen `"` gesetzt werden.


##### Config.UpdateRate
Alle wie viele Sekunden aktuelle Informationen an den LiveMap Server gesendet werden sollen.  
Niedriger: Aktuellere Daten in der LiveMap  
Höher: Weniger Serverlast, sowie Lag  
Ganzzahlwert zwischen 0 und 60


##### Config.JobNeeded
Muss der Spieler einen spezifischen Job haben, um auf der LiveMap angezeigt zu werden?
- Ja `true`
- Nein `false`


##### Config.Jobs
Eine Lua-Tabelle, welche Jobs auf der LiveMap angezeigt werden sollen und in welcher Farbe.
Zusätzlich kann eingeschränkt werden, auf welchen Systemen der Spieler angezeigt werden soll.
```lua
['job'] =    {['color'] = 2, ['system'] = "*"},
```
| **Farbe** | **Nummer** |
|-----------|------------|
| Weiß      | 1          |
| Blau      | 2          |
| Grün      | 3          |
| Rot       | 4          |
| Gelb      | 5          |

| **system** | **Beschreibung**           |
|-----------|----------------------|
| *       | Alle Systeme           |
| copnet  | Nur CopNet Systeme     |
| medicnet| Nur MedicNet Systeme   |
| carnet  | Nur CarNet Systeme     |

##### Config.NeededItem
Muss der Spieler ein Item im Inventar haben?
- Ja `Config.NeededItem = "ITEMNAME"`
- Nein `Config.NeededItem = nil`


##### Config.PlayerInVehicle
Muss der Spieler in einem Fahrzeug sein, um auf der Livemap angezeigt zu werden?
- Ja `true`
- Nein `false`


##### Config.AllowedVehicles
Welche Fahrzeuge sind zugelassen?  
Der Hash ist ein numerischer Wert, welcher von GTAV generiert wird. Diesen kannst du dir in FiveM mithilfe von [GetHashKey()](https://docs.fivem.net/natives/?_0xD24D37CC275948CC)  
```lua
[hash] = true
-- Beispiel:
[-1216765807] = true -- Adder
```


##### Config.CommandPanic
Soll der `/panic` Befehl aktiviert werden?
Der Panikmodus kann mit `/panic` aktiviert und mit `/panic reset` deaktiviert werden.  
- Ja `true`
- Nein `false`


##### Config.CommandGPS
Soll der `/gps` Befehl aktiviert werden? GPS deaktivieren: `/gps off`, GPS aktivieren: `/gps on`  
Mit diesem Befehl kann der Spieler sich selber von der LiveMap verschwinden/wieder anzeigen lassen
- Ja `true`
- Nein `false`


##### Config.RPName
Soll der RP-Name des Spielers angezeigt werden? Dies benötigt `esx-identity` um zu funktionieren.
- RP-Name `true`
- Steam-/FiveM-Name `false`


##### Config.ShowPanicNotfication
Soll, wenn ein Spieler den Panikmodus auslöst, alle Spieler mit dem selben Job benachrichtigt werden?
- Ja `true`
- Nein `false`

#### Datei
```lua
Config = {}
Config.Enable = true
Config.DebugMode = false
Config.PrivateKey = ""

-- Update Rate in secs
Config.UpdateRate = 1

-- If you need a specific job to be shown
Config.JobNeeded = true


--[[
Allowed jobs and the assigned blipcolor
color:
1 = white
2 = blue
3 = green
4 = red
5 = yellow

systems:
- copnet
- medicnet
- carnet
- * (All Systems)
]]
Config.Jobs = {
    ['police'] =    {['color'] = 2, ['system'] = "copnet"},
    ['ambulance'] = {['color'] = 4, ['system'] = "medicnet"},
    ['mechanic'] =  {['color'] = 5, ['system'] = "carnet"}
}

-- If item is needed in Inventory
-- "item name" or nil
Config.NeededItem = nil

-- If player needs to be in an vehicle
Config.PlayerInVehicle = false

-- Allowed Vehicle Hash
Config.AllowedVehicles = {
    [-1216765807] = true
}

-- Enable /panic command
Config.CommandPanic = true
-- Enable /gps command
Config.CommandGPS = true


-- Use the ESX identity Ingame name
-- Only works if ESX identity is installed
Config.RPName = true


-- Should everyone with the same job get a notification if someone panics
Config.ShowPanicNotfication = true

```

### Events
Das Skript stellt einige Schnittstellen zur verfügung, welche von anderen Skripten verwendet werden können  
Alle Events sind server-seitig, müssen aber vom Client aus angestoßen werden.

#### vcad-livemap:panic
Setzt den Panikmodus.
- Aktiv `true`
- Inaktiv `false`
```lua
TriggerServerEvent("vcad-livemap:panic", true)
```


#### vcad-livemap:disablegps
**Deaktiviert das GPS eines Spielers.**
- Deaktiviert `true`
- Aktiviert `false`

```lua
TriggerServerEvent("vcad-livemap:disablegps", true)
```
**Für andere Spieler:**
- spieler: ID des Spielers  

```lua
TriggerServerEvent("vcad-livemap:disableothergps", spieler, true) -- Clientseitig

TriggerEvent("vcad-livemap:disableothergps", spieler, true) -- Serverseitig
```