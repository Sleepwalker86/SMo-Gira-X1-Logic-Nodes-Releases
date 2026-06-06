# Release-Automatisierung

Dieses Repository ist die private Quelle fuer den Code. Veroeffentlicht wird nach:

```text
Sleepwalker86/SMo-Gira-X1-Logic-Nodes-Releases
```

Die GitHub Action `Publish public release` kopiert eine bestehende ZIP-Datei aus `Zip/` in das oeffentliche Release-Repository, synchronisiert die `README.md`, erstellt dort einen Commit und kann optional einen GitHub Release-Eintrag erzeugen.

## Einmalige Vorbereitung

Im privaten Source-Repository muss ein Repository Secret angelegt werden:

```text
PUBLIC_REPO_TOKEN
```

Der Token braucht Zugriff auf das oeffentliche Release-Repository und die Berechtigung, Inhalte und Releases zu schreiben.

## Release starten

In GitHub:

```text
Actions -> Publish public release -> Run workflow
```

Eingaben:

```text
zip_filename: sascha_moritz_web_de.Logic.Alarmanlage-1.4.3.zip
release_notes: Optionaler Beschreibungstext
```

Paketname und Version werden automatisch aus dem ZIP-Dateinamen gelesen. Ein GitHub Release wird immer erstellt oder aktualisiert.

Die Action erwartet dann diese Datei:

```text
Zip/sascha_moritz_web_de.Logic.Alarmanlage-1.4.3.zip
```

Weitere Beispiele:

```text
sascha_moritz_web_de.Logic.MQTTSubscribe-1.0.53.zip
sascha_moritz_web_de.Logic.MQTTServer-0.0.10.zip
sascha_moritz_web_de.Logic.Poolcontrol-1.0.21.zip
```

## Aktuelle Sicherheitsgrenze

Die Action baut und signiert noch nicht automatisch. Sie veroeffentlicht nur ZIPs, die bereits im privaten Repository vorhanden sind. Build und Signierung sollten separat nachgezogen werden, sobald Zertifikat und Passwort aus den Projektdateien in GitHub Secrets verschoben wurden.
