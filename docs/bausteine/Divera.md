# Logikbaustein Divera Gira X1

Der Logikbaustein ruft über die API von Divera in Verbindung mit dem API Key aktuelle Einsatzdaten ab.
Jedes mal wenn der Baustein am Eingang „Trigger“ eine 1 bekommt startet die Abfrage der Daten erneut.

Folgende Parameter werden an den Ausgängen ausgegeben:

- Einsatzalarm (0= kein Einsatz, 1= Einsatzalarm liegt an, Bool)
- Stichwort (Alarmstichwort, String)
- Meldung (Meldungstext, String)
- Adresse (String)
- Datum (Alarmierungszeitpunkt, DateTime)
- Sonderrechte (Bool)
- Angaben zum Gebäude (String)
- Anrufer (String)
- Patient (Zeichenfolge)
- Bemerkung (String)
- Anzahl gelesen (Integer)
- Einsatznummer (String)
- Impuls (Bool)
- Json (Ausgabe der kompletten Json Abfrage zum debuggen, String)


Folgende Eingänge/Parameter stehen zur Verfügung:
- Trigger (Startet den Baustein neu, Bool)
- API Key (Angabe des API Keys die von Divera bereitgestellt wird, String)
- User Filter (User ID zum Filtern ob der User beim Alarm adressiert ist, Integer)

Hinweis:
Der Intervall zum Triggern des Bausteins sollte nicht zu klein sein um des Gira X1 nicht zu überlasten.
Ein Intervall von 20-30 Sekunden ist sinnvoll.

## Changelog

Version 1.1.0
User Filter hinzugefügt um zu überprüfen ob der User mit einer bestimmten ID adressiert ist.
Die Ausgänge werden ab jetzt nur bei einer Wertänderung neu beschrieben. Vorher wurden die Ausgänge mit jedem triggern des Bausteins neu beschrieben.

Version 1.0.22
Ausgänge um die Einsatznummer und einen Impuls erweitert
Impuls wird ausgelöst wenn sich das Datum bzw. die Uhrzeit ändert.

Version 1.0.20
Abfangen von Nullwerten die ein Fehler des Baustein auslösen.

## Link zur Divera API Dokumentation
https://api.divera247.com/?urls.primaryName=api%2Fv1#/E

Verwendetes Icon:
https://www.flaticon.com/de/kostenlose-icons/alarm Alarm Icons erstellt von Freepik - Flaticon
