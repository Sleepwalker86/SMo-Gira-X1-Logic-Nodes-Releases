# Logikbaustein Tankerkoenig Gira X1

Dieser Baustein fragt aktuelle Spritpreise von Tankerkoenig.de ab.

Folgende Eingänge stehen zur Verfügung:
- Trigger (Bool)

Folgende Parameter stehen zur Verfügung:
- API Key (String)
- geographische Breite des Standortes
- geographische Länge
- Suchradius in km
- Spritsorte(e5, e10,diesel, all)
- Sortierung(price, dist)

Folgende Ausgänge stehen zur Verfügung:
- Json (String)
- Name (String)
- Straße (String)
- Distanz (Double)
- Diesel (Double)
- E5 (Double)
- E10 (Double)
- Offen (Bool)
- Hausnummer (String)
- PLZ (Integer)
- Preis (Double, Dieser Ausgang wird nur beschrieben wenn nach einer Spritsorte gefiltert wird)

## Changelog
V 1.0.8 Behebt den Fehler das wenn eine Tankstelle nicht für alle Kraftstoffe einen Preis zurück gibt der Download fehl schlägt.

API https://creativecommons.tankerkoenig.de/

Verwendetes Icon :<a href="https://www.flaticon.com/free-icons/gas-station" title="gas station icons">Gas station icons created by DinosoftLabs - Flaticon</a>
