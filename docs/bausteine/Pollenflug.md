# Logikbaustein Pollenflug Gira X1

Dieser Baustein fragt den Pollenflug-Gefahrenindex vom Deutschen Wetterdienst für drei Tage ab und gibt den Index an den entsprechenden Ausgang weiter.
Zusätzlich gibt es für jedes Gewächs einen Ausgang der bei überschreiten der eingestellten Schwelle für diesen Tag ein „True“ ausgibt.

Folgende Eingänge stehen zu Verfügung:
- Trigger (Bool)

Folgende Parameter stehen zu Verfügung:
- Region (Integer)
- Partregion (Integer)
- Warnschwelle(Integer, 1=niedrig,2=mittel,3=hoch)

Folgende Ausgänge stehen zu Verfügung:

- Roggen übermorgen (String)
- Roggen heute (String)
- Roggen morgen (String)
- Roggen Warnung (Bool)
- Beifuss übermorgen (String)
- Beifuss heute (String)
- Beifuss morgen (String)
- Beifuss Warnung (Bool)
- Birke übermorgen (String)
- Birke heute (String)
- Birke morgen (String)
- Birke Warnung (Bool)
- Graeser übermorgen (String)
- Graeser heute (String)
- Graeser morgen (String)
- Graeser Warnung (Bool)
- Esche übermorgen (String)
- Esche heute (String)
- Esche morgen (String)
- Esche Warnung (Bool)
- Hasel übermorgen (String)
- Hasel heute (String)
- Hasel morgen (String)
- Hasel Warnung (Bool)
- Erle übermorgen (String)
- Erle heute (String)
- Erle morgen (String)
- Erle Warnung (Bool)
- Ambrosia übermorgen (String)
- Ambrosia heute (String)
- Ambrosia morgen (String)
- Ambrosia Warnung (Bool)
- Region Name (String)
- Debug (String)

https://www.flaticon.com/de/kostenlose-icons/pollen Pollen Icons erstellt von Freepik - Flaticon



DWD Dokumentation: https://opendata.dwd.de/climate_environment/health/alerts/Beschreibung_pollen_s31fg.pdf
