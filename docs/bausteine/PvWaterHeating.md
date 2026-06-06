# Logikbaustein Pv Heizstab Steuerung Gira X1

Dieser Baustein Steuert PV geführt einen Heizstab für einen Warmwasserspeicher.

Folgende Eingänge stehen zu Verfügung:
- Freigabe (Bool)
- Aktuelle Leistung (Double, positiv=Überschuss / negativ=Bezug)
- Hausverbrauch (Double)
- Ist Temperatur (Double)

Folgende Parameter stehen zu Verfügung:
- Leistung invertieren (Bool)
- Nur PV (Bool)
- Soll Temperatur (Double)
- Leistung Stufe 1 (Integer, W oder KW)
- Leistung Stufe 2 (Integer, W oder KW)
- Leistung Stufe 3 (Integer, W oder KW)
- Toleranz Leistung (Integer, % von Stufe1)
- Umschaltpause(ms) (Integer)
- Regel Zeit(min) (Integer)
- Netzbezug erlauben (Bool)

Folgende Ausgänge stehen zu Verfügung:
- Stufe 1 (Bool)
- Stufe 2 (Bool)
- Stufe 3 (Bool)
- Debug (String)

Leistung Invertieren:
Je nach dem von wo aus die aktuelle Leistung betrachtet wird kann der Überschuss positiv oder Negativ sein.
Mit diesem Parameter könnt ich eure aktuelle Leistung anpassen bzw. invertieren.

Nur PV:
Dieser Parameter legt fest ob eure aktuelle Leistung am Haus Übergabepunkt gemessen wird oder ob ihr die aktuelle Leistung von der PV Anlage bekommt
Aus = aktuelle Leistung wird beim zuschalten einer Leistungsstufe um den Wert der Leistungsstufe reduziert
Ein = Egal ob der Verbraucher ein oder aus geschaltet ist bleibt die aktuelle Leistung gleich da es der Wert eurer PV Anlage ist

Hausverbrauch:
Mit diesem Wert rechnet der Baustein künstlich einen Eigenverbrauch vom Haushalt hinzu wenn ihre Leistung am Eingang „Aktuelle Leistung“ den Hausverbrauch nicht enthält.
Dies ist zb der Fall wenn sie nur die aktuelle erzeugte Leistung von ihrem Wechselrichter bekommen.

Parameter:
Leistung Stufe 1-3:
Hier müssen die Werte für die jeweilige Leistungsstufe in W oder KWh eingegeben werden.
Diese Werte dienen als Berechnungsgrundlage für die Entscheidung ob geheizt wird oder nicht.

Toleranz Leistung:
Dieser Wert wirkt sich unterschiedlich aus je nach dem ob Netzbezug erlaubt ist oder nicht.
Die Toleranz wird in % von der Angegebenen Leistung am Parameter „Leistung Stufe 1“ berechnet

- Netzbezug nicht erlaubt
Die Toleranz wird auf den Wert zur Auswertung addiert, sodass wenn zb. Leistungsstufe 1 500W beträgt und die
Toleranz 100W dann wird erst bei > 600W eingeschaltet.

- Netzbezug erlauben
Die Toleranz wird von dem Wert zur Auswertung abgezogen, sodass wenn zb. Leistungsstufe 1 500W beträgt und die
Toleranz 100W dann wird bereits bei > 400W eingeschaltet.

Umschaltpause:
Dieser Wert definiert in ms die Umschaltzeit zwischen ein uns ausschalten der einzelne Stufen.

Regel Zeit:
Diese Zeit wird gewartet bevor der Baustein die nächsten Leistungsvergleich bzw. Schaltung durchführt um ein ständiges ein und Ausschalten zu verhindern.

Netzbezug erlauben:
Hiermit wird definiert ob der Netzbezug erlaub wird.
Wenn der Netzbezug erlaubt wird Schalten die Ausgänge abzüglich der eingestellten Toleranz ein und nicht erst wenn für die jeweilige Stufe genug Überschuss vorhanden ist.
Selbes passiert ebenfalls beim ausschalten in umgekehrter Reihenfolge.

SOLL Temperatur:
Wenn der IST kleiner als der SOLL dann ist der Baustein aktiv und versucht auf die Sollwert Vorgabe zu heizen.
WICHTIG: Der verwendete Warmwasserspeicher muss zwingend einen eigenen separaten Temperaturfühler haben der den Heizstab bei erreichen der vom Hersteller vorgegebenen Maximaltemperatur abschaltet.
Das Kann nicht mittels KNX Komponenten abgebildet werden!!!!

Verwendetes Icon :https://www.flaticon.com/de/kostenlose-icons/photovoltaik Photovoltaik Icons erstellt von Khoirul Huda - Flaticon


## Changelog
Version 1.0.3
- Parameter “nur PV“ hinzugefügt für den fall das ihr nur euren erzeugten Wert von der PV Anlage bekommt
