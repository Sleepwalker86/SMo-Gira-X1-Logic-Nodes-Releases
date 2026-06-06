# Logikbaustein Alarmanlage

Diese Anleitung erklärt dir, wie du das Alarmsystem mit den verschiedenen Scharfschaltmodi (extern und intern), den Alarmzuständen und den Rücksetzungen bedienen kannst.
1. Modi des Alarmsystems
Du kannst das System in zwei Modi scharf schalten:
* Extern scharf: Sichert alle Türen, Fenster und Bewegungsmelder.
* Intern scharf: Sichert Türen und Fenster, jedoch ohne Bewegungsmelder.
2. Extern Scharfschalten
Voraussetzungen:
* Alle externen Sensoren (Türen, Fenster, Bewegungsmelder) müssen geschlossen sein.
* Der Alarmzustand muss inaktiv sein.
* Du musst die externe Scharfschaltung anfordern.
Ablauf:
* Das System startet einen Countdown, der durch den Parameter "verz. Extern Scharf (Sek.)" bestimmt wird.
* Nach Ablauf des Countdowns wird der Status auf "extern scharf" gesetzt, bis dahin kannst du das Gebäude verlassen da das öffnen einer Tür zu diesem Zeitpunkt noch nicht ausgewertet wird.
Deaktivierung:
* Wenn du die externe Scharfschaltung zurücksetzt, wird der Status auf "Bereit" gesetzt und der Scharfschaltvorgang gestoppt.
3. Intern Scharfschalten
Voraussetzungen:
* Alle Türen und Fenster müssen geschlossen sein.
* Der Alarmzustand muss inaktiv sein.
* Du musst die interne Scharfschaltung anfordern.
Ablauf:
* Das System startet einen Countdown, der durch den Parameter "verz. Intern Scharf (Sek.)" bestimmt wird.
* Nach Ablauf des Countdowns wird der Status auf "intern scharf" gesetzt.
Deaktivierung:
* Wenn du die interne Scharfschaltung zurücksetzt, wird der Status auf "Bereit" gesetzt.
4. Anlage in Bereitschaft setzen
Wenn weder die interne noch die externe Scharfschaltung aktiv ist und alle Sensoren korrekt geschlossen sind, setzt das System den Status auf "Bereit".
5. Alarm auslösen
Externer Alarm:
* Der externe Alarm wird ausgelöst, wenn das System extern scharf ist und ein Sensor (Türen, Fenster oder Bewegungsmelder) geöffnet wird.
* Die Sirene und das Blitzlicht werden aktiviert, und der Status wechselt auf "Einbruchalarm extern".
Interner Alarm:
* Der interne Alarm wird ausgelöst, wenn das System intern scharf ist und ein Sensor (Türen oder Fenster) geöffnet wird.
* Auch hier werden Sirene und Blitzlicht aktiviert, und der Status ändert sich auf "Einbruchalarm intern".
6. System zurücksetzen
Voraussetzungen:
* Der Reset-Button muss gedrückt werden.
* Der Alarmzustand muss aktiv sein.
* Es darf keine externe oder interne Scharfschaltung aktiv sein.
Ablauf:
* Durch das Drücken des Reset-Buttons deaktivierst du den Alarmzustand, setzt Sirene und Blitzlicht zurück und versetzt das System in den "Bereit"-Modus.
7. Fehlerdiagnose
Das System zeigt dir kontinuierlich den Zustand der externen und internen Scharfschaltung sowie den Status der Sensoren an. So kannst du den aktuellen Systemzustand immer überwachen.
8. Wichtige Parameter
* verz. Extern Scharf (Sek.): Verzögerung vor der Aktivierung des externen Scharfschaltens in Sekunden.
* verz. Intern Scharf (Sek.): Verzögerung vor der Aktivierung des internen Scharfschaltens in Sekunden.
* verz. Extern Alarm (Sek.): Verzögerung vor der Auslösung des externen Alarms in Sekunden.
* verz. Intern Alarm (Sek.): Verzögerung vor der Auslösung des internen Alarms in Sekunden.
9. Hinweise
* Achte darauf, dass alle Sensoren geschlossen sind, bevor du das System scharf schaltest.
* Im Alarmzustand musst du das System mit dem Reset-Button zurücksetzen, um die Alarmvorrichtungen zu deaktivieren.
* WICHTIG: Du musst die Eingänge die du verwendest als Initialwert von „1“ auf „0“ ändern damit die wenn noch kein Telegram eingetroffen ist der Eingang nicht pauschal auf true steht.



Beschreibung der Ein- und Ausgänge sowie Parameter des Alarmsystems

Eingänge
1. Extern Scharf (Bool)
    * Dieser Eingang aktiviert die externe Scharfschaltung des Systems. Wenn auf True gesetzt, sichert das System alle Türen, Fenster und Bewegungsmelder.
    * True: Extern scharf.
    * False: Extern unscharf.
2. Intern Scharf (Bool)
    * Dieser Eingang aktiviert die interne Scharfschaltung des Systems. Wenn auf True gesetzt, werden alle Türen und Fenster gesichert, die Bewegungsmelder bleiben jedoch deaktiviert.
    * True: Intern scharf.
    * False: Intern unscharf.
3. Reset (Bool)
    * Dieser Eingang setzt das Alarmsystem zurück. Wenn ein Alarm aktiv ist und der Eingang auf True gesetzt wird, deaktiviert er den Alarmzustand und setzt das System zurück in den "Bereit"-Modus.
    * True: System zurücksetzen.
    * False: Keine Aktion.
4. Tür 1 bis Tür 5 (Bool)
    * Diese Eingänge repräsentieren den Zustand der Türen. Wenn der Eingang einer Tür auf True gesetzt ist, bedeutet dies, dass die Tür geschlossen ist.
    * True: Tür geschlossen.
    * False: Tür offen.
5. Fenster 1 bis Fenster 10 (Bool)
    * Diese Eingänge repräsentieren den Zustand der Fenster. Ein Fenster ist geschlossen, wenn der entsprechende Eingang auf True gesetzt ist.
    * True: Fenster geschlossen.
    * False: Fenster offen.
6. Bewegung 1 bis Bewegung 10 (Bool)
    * Diese Eingänge überwachen die Bewegungsmelder. Wenn der Eingang eines Bewegungsmelders auf True gesetzt ist, zeigt dies, dass keine Bewegung detektiert wird.
    * True: Keine Bewegung erkannt.
    * False: Bewegung erkannt.
7. Technik 1 (Bool)
   * Dieser Eingang löst unabhängig von intern und extern Scharf aus.

Parameter
1. Verz. Extern Scharf (Sek.) (Integer)
    * Dieser Parameter bestimmt die Verzögerung in Sekunden, bevor die externe Scharfschaltung aktiviert wird. Nach der Anforderung zur externen Scharfschaltung wartet das System diese Zeitspanne ab, bevor es den Status auf "extern scharf" setzt.
2. Verz. Intern Scharf (Sek.) (Integer)
    * Dieser Parameter legt die Verzögerung in Sekunden fest, bevor die interne Scharfschaltung aktiviert wird. Nach der Anforderung zur internen Scharfschaltung wartet das System diese Zeitspanne, bevor es den Status auf "intern scharf" setzt.
3. Verz. Extern Alarm (Sek.) (Integer)
    * Dieser Parameter gibt an, wie lange das System warten soll, bevor der externe Alarm ausgelöst wird, nachdem ein Tür Sensor eine Störung (geöffnete Tür) meldet.
    * WICHTIG: Die Alarm Verzögerung wirkt sich nur auf die Tür Eingänge aus. Alle anderen Sensoren führen sofort zu einem Alarm!
4. Verz. Intern Alarm (Sek.) (Integer)
    * Hier wird die Verzögerung in Sekunden eingestellt, bevor der interne Alarm ausgelöst wird, nachdem ein Tür Sensor eine Störung (geöffnete Tür) meldet.
    * WICHTIG: Die Alarm Verzögerung wirkt sich nur auf die Tür Eingänge aus. Alle anderen Sensoren führen sofort zu einem Alarm!
5. Sensoren NC = 1 / NO = 0 (Bool)
    * Dieser Parameter bestimmt, ob die Sensoren als Normal geschlossen (NC) oder Normal offen (NO) konfiguriert sind.
    * True (1): Sensoren arbeiten im Normal-geschlossen-Modus (NC).
    * False (0): Sensoren arbeiten im Normal-offen-Modus (NO).
6. Sirene Timer (Sek.) (Integer)
    * Hier wird die Verzögerung in Sekunden eingestellt, bis die Sirene nach einem Alarm deaktiviert wird. Jede neue Melder Änderung aktiviert die Sirene und den Timer erneut.

Ausgänge
1. Sirene (Bool)
    * Dieser Ausgang wird aktiviert, wenn ein Alarm ausgelöst wird. Wenn auf True gesetzt, wird die Sirene aktiviert.
    * True: Sirene aktiv.
    * False: Sirene inaktiv.
2. Blitzlicht (Bool)
    * Dieser Ausgang wird ebenfalls bei einem Alarm aktiviert. Wenn auf True gesetzt, wird das Blitzlicht eingeschaltet.
    * True: Blitzlicht aktiv.
    * False: Blitzlicht inaktiv.
3. Status Extern Scharf (Bool)
    * Dieser Ausgang zeigt an, ob das System extern scharf ist. Wenn auf True gesetzt, ist die externe Scharfschaltung aktiv.
    * True: Extern scharf.
    * False: Extern unscharf.
4. Status Intern Scharf (Bool)
    * Dieser Ausgang zeigt an, ob das System intern scharf ist. Wenn auf True gesetzt, ist die interne Scharfschaltung aktiv.
    * True: Intern scharf.
    * False: Intern unscharf.
5. Betriebszustand (String)
    * Dieser Ausgang gibt den aktuellen Betriebszustand des Systems als Text aus, z.B. "Bereit", "extern scharf", "Einbruchalarm extern" usw.
6. Debug (String)
    * Dieser Ausgang gibt eine detaillierte Diagnose des Systems aus, wie z.B. den Status der Sensoren, ob die externe oder interne Scharfschaltung aktiv ist, und ob der Alarmzustand aktiviert ist.

## Changelog

    Version 1.4.1:
    - Bugfix: Scharfschaltung fehlgeschlagen – Der Ausgang "Scharfschaltung fehlgeschlagen" wurde bisher nur bei fehlgeschlagener externer Scharfschaltung ausgelöst. Bei "Intern Scharf" wurde der Fehler-Output nicht gesetzt, obwohl Sensoren offen waren. Behoben: Error_Scharfschaltung wird nun bei beiden Scharfschaltungsarten korrekt auf true gesetzt.
    - Bugfix: Scharfschaltung fehlgeschlagen (Error_Scharfschaltung) – Der Ausgang "Scharfschaltung fehlgeschlagen" wird nun bei jedem fehlgeschlagenen Scharfschaltversuch erneut als false→true Flanke gesendet, auch wenn der Wert zuvor bereits true war. Zudem zeigt der Betriebszustand bei fehlgeschlagener Scharfschaltung jetzt "nicht bereit!" für 5 Sekunden an, bevor er automatisch auf die aktuelle Sensoranzeige zurückspringt. Die Prüfung CheckInternState() wurde aus der Einstiegsbedingung für "Intern Scharf" entfernt und in den Callback verlagert (analog zu "Extern Scharf"), sodass auch bei intern offenen Sensoren eine korrekte Fehlermeldung erfolgt.
    - Bugfix: Fehlende Rückmeldung bei fehlgeschlagener Scharfschaltung – Bei fehlgeschlagener Scharfschaltung wurden die Ausgänge "Status Extern Scharf" bzw. "Status Intern Scharf" nicht erneut gesendet, da der Wert bereits false war. Schalter und Visualisierungen blieben dadurch in der "Scharf"-Stellung hängen. Behoben: Die Status-Ausgänge werden nun bei fehlgeschlagener Scharfschaltung explizit auf false gesetzt und als Event gesendet, sodass sich alle angebundenen Schalter/Visualisierungen direkt zurücksetzen.

    Version 1.4.0:
    - Fehler behoben das wenn die Verzögerungszeit beim Extern Scharfschalten aktiv ist und dann zb. Zyklisch ein Melder Telegramm eintrifft, der Status fälschlicherweise wieder auf         "Bereit" gesetzt wurde.
    - zwei weitere Sirenen Ausgänge hinzugefügt um vom Internen und Externen Alarm unterscheiden zu können.
        Sirene Extern: Wird nur aktiv wenn ein Alarm anliegt im Modus Extern Scharf
        Sirene Intern: Wird nur aktiv wenn ein Alarm anliegt im Modus Intern Scharf
        Sirene: Wird aktiv wenn ein Alarm anliegt im Modus Extern/Intern Scharf
    - Die möglichkeit hinzugefügt die Texte an dem Status Ausgang selbst zu ändern für zb. andere Sprachen
        - Text ändern für: Bereit, wird scharfgeschaltet.., Extern Scharf, Intern Scharf, Einbruchalarm Extern, Einbruchalarm Intern

    Version 1.3.2:
    - Fehler behoben das die Status Ausgänge permanent senden und den Bus mit Telegrammen fluten.

    Version 1.2:
    - Ausschalt Timer für die Sirene hinzugefügt. Wenn die Zeit verstrichen ist schaltet die Sirene aus
     - Jede neue Alarmauslösung triggert die Alarmausgänge erneut(Sirene/Blitzleuchte)

    Version 1.1.0:
    - Anzahl für die Fensterkontakte von 10 auf 20 erhöht.
     - Technik Alarm Eingang hinzugefügt.

    Version 1.0.1:
    - Wenn die Verzögerung aktiv ist und ein Sensor nicht geschlossen ist kommt ein Fehler. Vorher wurde trotzdem scharf geschaltet.

     Version 1.3.0:
          - Wenn die Verzögerung aktiv ist und ein Sensor nicht geschlossen ist kommt ein Fehler. Vorher wurde trotzdem scharf geschaltet.
        - Ausgang „Scharfschaltung fehlgeschlagen„ hinzugefügt. Dieser Ausgang kann verwendet werden um den Fehler zu signalisieren. Zb. als         Lichtsignal oder Push Nachricht.
        - Ausgang „Alarmverzögerung aktiv“ hinzugefügt. Dieser Ausgang kann verwendet werden um zb im Eingangsbereich mit einem Licht daran zu     erinnern das die Anlage noch scharf geschaltet ist.
        - Fehler behoben wenn die Anlage intern Scharf geschaltet ist, ein Bewegungsmelder den Zustand ändert dann wurde fälschlicherweise der         Betriebszustand von „intern Scharf“ auf „Bereit“ gewechselt.
        - Eingang „Bewegung 1“ führt nicht mehr direkt zum auslösen der Alarmanlage sondern verhält sich genau so wie die Tür 1. Dieser Eingang kann     für den Bewegungsmelder verwendet werden, der im Eingangsbereich installiert ist um ein             betreten des Sicherheitsbereich zu gewährleisten.

    Version 1.3.2:
    - Es wurde ein Fehler behoben der permanent den Status Intern und Extern Scharf sendet
