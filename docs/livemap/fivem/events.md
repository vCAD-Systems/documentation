# Events und Befehle

### Befehle
In allen FiveM-Versionen der vCAD-LiveMap gibt es folgende Befehle:  

#### /panic
Der /panic Befehl löst den Panikmodus aus.  

Panikmodus auslösen:  
```
/panic
```
Panikmodus zurücksetzen:  
```
/panic reset
```
Du hast bereits ein Panik-Skript auf deinem Server? Kein Problem, deaktiviere den Befehl einfach in der `config.lua`. Setze dazu `Config.CommandPanic` auf `false`.  
Unten findest du weitere Informationen, wie du den Panikmodus auch von einem anderen Skript aus auslösen kannst.


#### /gps
Mit dem /gps Befehl kann der Spieler kontrollieren, ob er auf der LiveMap angezeigt wird.  
GPS ausschalten (von der LiveMap verschwinden):
```
/gps off
```
GPS einschalten (auf der LiveMap erscheinen):
```
/gps on
```
Standardmäßig ist das GPS an.  
Falls du dieses System mit einem eigenen Skript verknüpfen möchtest, kannst du ebenfalls den Befehl in der `config.lua` deaktivieren. Setze dazu `Config.CommandGPS` auf `false`.  
Informationen zu Events sind unten zu finden.

### Events
Die vCAD-LiveMap stellt folgende FiveM-Events zur Verfügung:

#### vcad-livemap:panic
Setzt den Panikmodus des aktuellen Spielers.
- Aktiv `true`
- Inaktiv `false`
```lua
TriggerServerEvent("vcad-livemap:panic", true) -- Clientseitig
```


#### vcad-livemap:disablegps
**(De-)Aktiviert das GPS des aktuellen Spielers.**
  - Deaktiviert `true`
  - Aktiviert `false`

```lua
TriggerServerEvent("vcad-livemap:disablegps", true) -- Clientseitig
```
**Für andere Spieler**:
  - spieler: ID des Spielers

```lua
TriggerServerEvent("vcad-livemap:disableothergps", spieler, true) -- Clientseitig
TriggerEvent("vcad-livemap:disableothergps", spieler, true) -- Serverseitig
```
