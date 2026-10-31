# Teil 11: Automationen

Ziel: Wiederkehrendes läuft von selbst: beim Ende einer Sitzung und freitags nach Zeitplan. Dauer zum Mitmachen: ca. 60 Minuten. Voraussetzung: [Teil 10](10-knowledge-base.md) (mindestens Teil 5, denn ohne Repo gibt es nichts hochzuladen).

## Video

{{VIDEO_11}}

Länge: 02:33

## Was du brauchst

- Das Repo auf GitHub aus Teil 5, die Tagesnotizen (Teil 4) und die Knowledge Base (Teil 10).
- Für die geplante Aufgabe: die **Claude-Desktop-App** ([claude.com/download](https://claude.com/download)). Laut Doku ab Version 1.1.5368. Anleitung: [code.claude.com/docs/en/desktop-scheduled-tasks](https://code.claude.com/docs/en/desktop-scheduled-tasks)
- Kosten: im Claude-Abo enthalten.

Es gibt drei Arten von Auslösern:

| Auslöser | Was er tut | Beispiel |
|---|---|---|
| **Hook** | reagiert auf ein Ereignis in Claude Code | Ende einer Sitzung: sichern und hochladen |
| **Zeitplan** | startet eine Aufgabe zu einer festen Zeit | freitags 14 Uhr der Wochenbericht |
| **Workflow-Werkzeug** (zum Beispiel n8n) | verbindet Dienste: wenn X passiert, dann Y | nicht Teil dieses Videos |

Ein Hook läuft mit deinen Rechten und ohne Rückfrage. Trage nur Befehle ein, die du verstehst, keine, die etwas löschen.

## Schritt für Schritt

1. **Claude:** Bitte Claude um einen Hook. Prompt in Claudian:

   ```text
   Richte mir einen Hook ein: Wenn eine Sitzung endet, sollen Tagesnotiz und Knowledge Base committet und gepusht werden. Fehler sollen in eine Log-Datei geschrieben werden, damit nichts still scheitert. Zeig mir vorher, was du in die settings.json schreibst, und teste es danach mit einer kurzen Sitzung.
   ```

   Der Auftrag sagt, **wann** etwas passieren soll (Sitzung endet), **was** (committen und pushen), **wohin Fehler gehen** (Log-Datei) und dass Claude dir **vorher zeigt**, was es einträgt, und **danach testet**. So baust du jede Automation.

2. **Du:** Claude ändert noch nichts, sondern zeigt zuerst die `settings.json` und den Testplan. Der Hook ruft am Ende jeder Sitzung ein kleines Skript auf. Es speichert Tagesnotiz und Knowledge Base und lädt sie hoch. Fehler landen in einer Log-Datei.

3. **Claude:** Gib frei:

   ```text
   Passt so, das Log bleibt im Repo. Leg los und teste es.
   ```

   „Im Repo“ heißt hier: im Projektordner. Claude schließt die Log-Datei per `.gitignore` vom Hochladen aus.

   Claude richtet alles ein und testet echt: eine kurze Sitzung, danach liegt ein neuer Speicherpunkt auf GitHub. Der Tester prüft auch die Fehlerfälle. Geht etwas schief, steht es im Log, statt still zu scheitern.

4. **Du:** Öffne dein Repo auf github.com. Ein neuer Speicherpunkt, den du nicht selbst gemacht hast, zeigt: Der Hook läuft.

5. **Claude:** Jetzt der Zeitplan. Starte eine **neue Sitzung** und frage:

   ```text
   Wie lasse ich den Wochenbericht jeden Freitag um 14 Uhr von allein schreiben? Ich arbeite auf einem Mac. Erklär es mir kurz, ändere noch nichts.
   ```

   Auf Windows: ersetze „auf einem Mac“ durch „auf Windows“. Claude nennt Wege.

6. **Claude:** Frage nach, wenn etwas nicht passt:

   ```text
   Gibt es einen einfacheren Weg ohne Terminal? Und der Kalender kommt doch über den Connector, nicht über die Kalender-App vom Mac, oder?
   ```

   Im Video hatte Claude zuerst etwas Falsches über den Kalender behauptet, gab den Fehler auf Nachfrage zu und nannte einen einfacheren Weg: eine geplante Aufgabe in der Claude-App auf deinem Rechner. Nachfragen lohnt sich immer.

7. **Du:** Lege die geplante Aufgabe in der Claude-App an. **Die Menünamen sind laut Doku englisch und am Mac noch nicht durchgeklickt (ungeprüft).**
   1. Öffne die Claude-Desktop-App und wechsle in den Bereich **Code**.
   2. Öffne **Scheduled** (ggf. heißt es „Routines“) und wähle **New task** (ggf. „Set up manually“).
   3. Gib der Aufgabe einen **Namen** und die **Anweisung** (Beispiel unten).
   4. Öffne **Advanced settings** und wähle **Only on this computer**. Setze den **Local folder** auf deinen Vault.
   5. Stelle den **Schedule** auf wöchentlich, Freitag, 14:00.

   Die App muss offen und der Rechner wach sein. Anweisung (Beispiel):

   ```text
   Nutze den Skill wochenbericht und schreibe den Bericht dieser Woche. Nichts versenden, nichts überschreiben.
   ```

**Platzhalter:** „Ich arbeite auf einem Mac“ ersetzt du durch dein System. „Freitag 14 Uhr“ ist das Beispiel aus dem Video. Der Skill `wochenbericht` stammt aus Teil 7; hast du ihn anders genannt, nimm deinen Namen.

## Das siehst du im Video

| Zeit | Szene |
|---|---|
| 00:00 | Einstieg: Wer sich auf sein Gedächtnis verlässt, vergisst es im Stress, Titel „Teil 11: Automationen“ |
| 00:15 | Prinzip: drei Auslöser (Hook, Zeitplan, Workflow) |
| 00:32 | Der Prompt für den Hook, „Ich habe noch nichts geändert“ |
| 00:42 | Der Prompt noch einmal in Ruhe: wann, was, wohin Fehler gehen, vorher zeigen, danach testen |
| 01:01 | Der Vorschlag: `settings.json` mit `SessionEnd`, der Testplan |
| 01:15 | Getestet: Freigabe, „Der Hook läuft“, „Geprüft, mit Beleg“ |
| 01:31 | Freitags, 14 Uhr: die Frage, Claudes Empfehlung über das Terminal mit einer falschen Aussage zum Kalender |
| 01:45 | Nachfragen: Claude gibt den Fehler zu, nennt den einfacheren Weg |
| 02:00 | Geplante Aufgabe in der Claude-App: Schritte laut Anleitung von Anthropic |
| 02:19 | Fertig, wenn …, Ausblick auf Teil 12 |

## Wenn es bei dir anders aussieht

- **Die Menüs der Claude-App sind nicht aufgenommen.** Das Video zeigt die Schritte nach der offiziellen Doku (Menünamen englisch). Am Mac wurden sie noch nicht durchgeklickt. Bei dir können „Scheduled“, „Routines“, „New task“, „Set up manually“ anders heißen oder an anderer Stelle stehen.
- **Claude legt den Hook als Projekt-Hook an.** Im Video: Datei `.claude/settings.json`, Ereignis `SessionEnd`, Skript `.claude/hooks/session-end-sync.sh`, `timeout` 120 Sekunden. Die Log-Datei wird per `.gitignore` nicht hochgeladen.
- **Getestet wird mit einer Kurzsitzung** (`claude -p`), die Fehlerfälle in einem Wegwerf-Klon des Repos.
- **Claude empfiehlt dir vielleicht einen anderen Weg als im Video.** Im Video nannte es nach der Korrektur zwei Wege: die geplante Aufgabe in der Claude-App (empfohlen) und eine Cloud-Routine. Die Cloud-Routine arbeitet auf einer frischen Kopie deines Repos, der Hook läuft dort nicht, und ein Skill, der nicht im Repo liegt, fehlt dort.
- **Ob Claudian beim Schließen eines Chats den Hook `SessionEnd` auslöst**, ist **ungeprüft**. Getestet wurde er im Video mit einer Kurzsitzung im Terminal.
- **Hook unter Windows.** Das Skript im Video ist ein Shell-Skript (`.sh`). Wie Claude es unter Windows umsetzt, ist **ungeprüft**.
- **Eine Automation, die lautlos nicht auslöst, ist die gefährlichste Sorte.** Baue immer einen Beleg ein (Log, neuer Commit).
- **Du willst den Fehlerfall selbst sehen:** Bitte Claude, absichtlich einen Fehler auszulösen und im Log zu zeigen. Ein Beispielprompt (nicht im Video): „Löse für den Test absichtlich einen Fehler im Hook aus, zeig mir den Eintrag im Log und mach den Fehler danach wieder rückgängig.“
- **n8n selbst betrieben** ist laut Lizenz nur für interne oder nicht-kommerzielle Zwecke frei.

## Fertig, wenn …

- [ ] Nach einer Sitzung liegt ein neuer Speicherpunkt auf GitHub, ohne dass du etwas getan hast.
- [ ] Ein absichtlich ausgelöster Fehler steht in der Log-Datei.
- [ ] `/hooks` zeigt deinen Hook (im Terminal).

## Wenn du hängst

```text
Ich komme bei Teil 11 (Hook und geplante Aufgabe) nicht weiter. Ich habe [Mac oder Windows]. Das passiert: [beschreibe, was du siehst]. Zeig mir, welche Hooks eingerichtet sind und was in der Log-Datei steht, und führ mich Schritt für Schritt zur Lösung. Ändere nichts, bevor du es mir gezeigt hast.
```

[Weiter: Teil 12 Mehrere Rechner](12-mehrere-rechner.md)
