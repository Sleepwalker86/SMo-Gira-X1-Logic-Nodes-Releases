# Logikbaustein MQTT Publish Gira X1

Dieser Baustein sendet beim eintreffen eines Telegramm am Eingang „Message“ einen String an einen MQTT Broker mit dem angegebenen Topic.

Folgende Eingänge stehen zur Verfügung:
- Message (String)

Folgende Parameter stehen zur Verfügung:
- Host (IP Adresse des Brokers, String)
- Port (Integer)
- Topic (String)
- Username (String)
- Password (String)

Folgende Ausgänge stehen zur Verfügung:
- Debug (String)

## Changelog
Version: 1.0.6
- Baustein um Username, Password und Port erweitert
