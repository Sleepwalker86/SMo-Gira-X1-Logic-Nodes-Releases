# Logikbaustein Divera Status Rückmeldung

Beschreibung
Der Logikbaustein setzt einen User Status über die Divera API.
Es besteht die Möglichkeit einen zuvor definierten Status per Trigger zu setzen oder  eine ID an den Eingang „Status ID“  zu senden um somit flexibel einen Status setzen zu können.

Folgende Eingänge stehen zur Verfügung:
- Trigger (Bool)
- Status ID (Integer)

Folgende Parameter stehen zur Verfügung:
- Benutzer API Key (String)

Folgende Ausgänge stehen zur Verfügung
- Erfolg (Bool)
- Debug (String)

Trigger:
Trifft an dem Eingang eine 1 ein, sendet der Baustein den Status mit der ID die am Eingang „Status ID“

Status ID:
Trifft an dem Eingang Zahl ein die einem in Rivera angelegten Status gleicht wird dieser status gesendet.
Der Status wird ab „1“ aufwärts gezählt. Zb. 1 = Verfügbar, 2 = nicht Einsatzbereit etc…..

Benutzer API Key:
Hier müsst ihr euren eigenen Benutzer API Key angeben den ihr in euren Accounteinstellungen findet (Einstellungen/Debug)

Link zur Divera API Dokumentation:
https://api.divera247.com/?urls.primaryName=api%2Fv1#/E
Verwendetes Icon:
https://www.flaticon.com/de/kostenlose-icons/alarm Alarm Icons erstellt von Freepik – Flaticon
