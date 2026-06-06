# Logikbaustein MQTT Subscribe Gira X1

Dieser Baustein empfängt eine Nachricht von einen MQTT Server mit dem angegebenen Topic und leitet diese an den Ausgang  „Message“ weiter.(String)
Folgende Eingänge stehen zur Verfügung:
- Enable(Bool, Hier muss der Datenpunkt vom X1 “Bereit” angegeben werden)
Folgende Parameter stehen zur Verfügung:
- Host (IP Adresse des Brokers, String)
- Port (Integer)
- Topic (String)
- Username (String)
- Password (String)
- Restart( Hier kann die Zeit in Stunden angegeben werden um die Verbindung erneut aufzubauen, 0=aus, Integer)
Folgende Ausgänge stehen zur Verfügung:
- Message(Ausgabe von der empfangenen Nachricht, String, QoS 0)
- Debug(Ausgabe von Fehlern, String)

Wenn man zb. Temperaturwerte empfangen möchte kann man am Ausgang des Baustein ein Typ Converter anhängen um anschließen mit den Werten auch rechnen zu können.
Dieser Baustein muss in der Simulation im GPA vorm beenden der Simulation am Eingang “Enable” mit einer 0 beendet werden.

## Changelog
Version 1.0.50
- Baustein um Username, Password und Port erweitert
