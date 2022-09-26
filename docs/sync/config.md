# vCad-Sync  -  config.lua

### Config.ApiKey

Hier müsst ihr euren ApiKey eintragen, damit das System weiß, auf welches Netzwerk zugegriffen werden muss.

### Config.Computer

Hier habt ihr die Möglichkeit die User mit allen erstellten PC´s zu syncronisieren oder ihr gebt nur die PC ID´s an, wo die Akten erstellt werden sollen.

- `Config.Computer = 'all'`  
Erstellt auf allen PC´s die Akten.

- `Config.Computer = {1, 5}`  
Erstellt z.B nur auf PC 1 und 5 die Akten.

### Config.Sync_HairColor

Hier habt Ihr selbst die Entscheidung ob Ihr die Haarfarbe auch synchronisieren wollt.  
Beachtet aber, dass ihr die Haarfarbe je nach Ziffer selber in der hair.lua im Config Ordner einstellen müsst.  
Habt Ihr keine modded Haarfarben drin, sind die aktuellen Ziffern in der hair.lua richtig.

### Config.Sync_EyeColor

Hier habt ihr selbst die Entscheidung, ob ihr die Aufenfarbe auch synchronisieren wollt.  
Beachtet hierbei, das ihr die Augenfarbe je nach Ziffer selber in der eye.lua im Config Ordner einstellen müsst.  
Habt ihr keine modded Augenfarben drin, sind die aktuellen Ziffern in der hair.lua richtig.

### Config.Admins

Hier könnt ihr einstellen, welcher Admin selbständig Fahrzeuge in der `vehicle.lua` im Config Order hinzufügen darf.  
Dies ist ingame mit dem Befehl `"vCAD-Car"` möglich.

### Config.CharakterSync

Hier könnt Ihr den kompletten Charakter Sync ausschalten, wenn nur der Fahrzeug Sync erwünscht ist.
Stellt dazu einfach die Config auf `Config.CharakterSync = false`.

### Config.Multichar

Hier gibt es nun 2 Varianten, wenn Ihr allerdings von Datenbank wenig Ahnung habt, und keine ID Spalte in der "users" Tabelle habt, stellt einfach
Activated auf true.

Für die Fortgeschrittenen unter uns:
Ihr habt bereits eine Auto_Increment Spalte? Tragt diese einfach in Anführungszeichen ein z.B Spalte = "SPALTENNAMEN"
Sollte eure Spalte allerding auch "id" heißen, so könnt auch ihr Spalte einfach auf nil stehen lassen.

### Config.vehicle

Ihr wollt, dass das Kfz-Register automatisch gefüllt wird?  
Dann setzt Activated einfach auf = true

### Config.VehicleColor

Ihr habt zusätzlich noch weitere Fahrzeug Farben? z.B Modded, dann müsst ihr diese hier nachtragen.
Habt ihr nur die Standard GTA Farben, könnt ihr das so lassen.  
Die Zahl `['17']` ist immer die Color-Nummer, und nach dem Gleichheitszeichen steht, was in der Fahrzeugakte eingetragen wird z.B `"Util Dark silver"`

### Config.VehiclesList

Ihr seit fortgeschritten und wollt es lieber manuell eingeben?  
Ganz einfache und kurze erklärung...

`Type:` Ist im Fahrzeug-Register die Spalte Fahrzeugtyp.  
`Label:` Ist im Fahrzeug-Register die Spalte Fahrzeug.  
`Hash:` Dort müsst Ihr das Model eintragen.  

Für die Anfänger empfehle ich, wie oben schon erwähnt, einfach den ingame Befehl `vCAD-Car`. Setzt euch dafür in das Fahrzeug, was ihr in der Kategorie 
hinzufügen wollt und gibt den Befehl in der `F8` Console, oder im chat mit einem `/` davor, ein. `/vCAD-Car`