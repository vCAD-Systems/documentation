#config.lua

###Config.PrivateKey

Hier müsst Ihr eure PrivateKey eintragen, damit unser Server weiss auf Welches Netzwerk dieser zugreifen muss.

###Config.Computer

Hier habt Ihr die möglichkeit die Users mit Allen erstellten PC´s zu Syncen,
oder Ihr gebt nur die PC ID´s an wo die Akten erstellt werden sollen.

-Config.Computer = 'all'

Erstellt auf allen PC´s die Akten.

-Config.Computer = {1, 5}

Erstellt z.B nur auf PC 1 und 5 die Akten.

###Config.Sync_HairColor

Hier habt Ihr selbst die Entscheidung ob Ihr die Haarfarbe mit Syncen wollt.

beachtet aber das Ihr die Haarfarbe je nach Ziffer selber in der hair.lua im Config Ordner einstellen müsst.

Habt Ihr keine Modded Haarfarben drin, sind die Aktuellen Ziffern in der hair.lua richtig.

###Config.Sync_EyeColor

Hier habt Ihr selbst die Entscheidung ob Ihr die Aufenfarbe mit Syncen wollt.

beachtet aber das Ihr die Augenfarbe je nach Ziffer selber in der eye.lua im Config Ordner einstellen müsst.

Habt Ihr keine Modded Augenfarben drin, sind die Aktuellen Ziffern in der hair.lua richtig.

###Config.Admins

Hier könnt Ihr einstellen welcher Admin selbständig Fahrzeuge in der vehicle.lua im Config Order hinzufügen darf.

dies geschiet ingame mit dem Befehl ####vCAD-Car.

###Config.Multichar

Hier gibt es nun 2 Varianten, wenn Ihr allerdings von Datenbank wenig Ahnung habt, und keine ID Spalte in der "users" Tabelle habt, stellt einfach
Activated auf true.

für die Fortgeschrittenen unter uns:
Ihr habt bereits eine Auto_Increment Spalte? tragt diese einfach in Anführungszeichen ein z.B Spalte = "SPALTENNAMEN"
Sollte eure Spalte allerding auch "id" heißen so könnt auch ihr Spalte einfach auf nil stehen lassen.

###Config.vehicle

Ihr wollt das Kfz-Register Automatisch gefüllt wird?

so setzt Activated einfach auf = true

###Config.VehicleColor

Ihr habt zusätzlich noch weitere Fahrzeug Farben? z.B Modded so müsst Ihr diese Hier nachtragen.
habt Ihr nur die Standard GTA Farben so könnt Ihr das so lassen.

Die Zahl `['17']` ist immer die Color Nummer, und nach dem gleichzeichen steht das was in der Fahrzeug Akte eingetragen wird z.B `"Util Dark silver"`

###Config.VehiclesList

Ihr seit fortgeschritten und wollt es lieber Manuell eingeben?

ganz einfache und kurze erklärung...

`Type:` ist im Fahrzeug Register die Spalte Fahrzeugtyp.
`Label:` ist im Fahrzeug Register die Spalte Fahrzeug.
`Hash:` dort müsst Ihr das Model eintragen.

Für die Anfänger Empfehle ich wie oben schon erwähnt einfach den ingame Befehl `vCAD-Car`, Setzt euch einfach dafür in das Fahrzeug was Ihr in der Kategorie 
hinzufügen wollt und gibt den Befehl in der `F8` Console ein, oder im chat mit einem `/` davor. `/vCAD-Car`