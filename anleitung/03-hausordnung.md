# Teil 3: Die Hausordnung

Ziel: Claude kennt deine Regeln bei jedem Start, ohne dass du sie wiederholst. Dauer zum Mitmachen: ca. 30 Minuten. Voraussetzung: [Teil 2](02-arbeitsplatz.md).

## Video

[Video ansehen (MP4, 15 MB)](https://github.com/marcgarding54-create/AI-OS/releases/download/v1.0/teil-03-hausordnung.mp4)

Länge: 02:17

## Was du brauchst

- Obsidian mit Claudian aus Teil 2 (oder Claude Code im Terminal).
- Die Datei „00 Kontext/Über mich.md“ aus Teil 2. Die Hausordnung verweist darauf.
- Nichts zu installieren. Hintergrund: [Wie Claude sich dein Projekt merkt (offizielle Doku zu CLAUDE.md)](https://code.claude.com/docs/en/memory)

Die Hausordnung ist eine Textdatei namens `CLAUDE.md`. Claude Code liest sie bei jedem Start automatisch. Was darin steht, gilt, bis du es änderst. Es gibt zwei Ebenen:

| Ebene | Wo sie liegt | Wofür |
|---|---|---|
| Global | Mac: `~/.claude/CLAUDE.md`, Windows: `%USERPROFILE%\.claude\CLAUDE.md` | gilt überall: Sprache, Ton, Arbeitsweise, was nie ohne Rückfrage geschieht |
| Projekt | `CLAUDE.md` im Projektordner | gilt nur dort, hier für den Wochenbericht |

## Schritt für Schritt

1. **Claude:** Lass Claude die globale Hausordnung schreiben. Schreib den Prompt in Claudian:

   ```text
   Leg mir eine globale CLAUDE.md an. Frag mich vorher nacheinander: In welcher Sprache und wie ausführlich soll ich antworten? Was soll ich vor größeren Aufgaben tun? Was darf ich nie ohne Rückfrage tun? Woran erkenne ich, dass eine Aufgabe wirklich fertig ist? Halte die Datei unter 40 Zeilen und verweise auf „00 Kontext/Über mich.md“.
   ```

2. **Du:** Claude stellt die vier Fragen nacheinander als Auswahlfelder: Sprache, Vorgehen bei größeren Aufgaben, No-Gos, „fertig“. Klicke die Antworten an. Heraus kommt eine kurze Datei (im Video 25 Zeilen). Kurz ist Absicht: Jede Regel kostet bei jedem Start Aufmerksamkeit.

3. **Claude:** Lass einen Wochenbericht schreiben, an dem du eine Projektregel festmachen kannst:

   ```text
   Schreib aus woche-43 den Wochenbericht für Woche 43.
   ```

4. **Du:** Schau dir den Bericht an. Im Video enthält er einen leeren Abschnitt. Das ist der Anlass für eine Regel.

5. **Claude:** Korrigiere und lass Claude daraus eine Regel für dieses Projekt machen:

   ```text
   Streich den leeren Abschnitt. Und mach daraus eine Regel für dieses Projekt: Ein Wochenbericht hat höchstens eine Seite, nur Stichpunkte, keine leeren Abschnitte und ist freitags fertig.
   ```

   Claude legt eine `CLAUDE.md` im Vault an.

6. **Du:** Starte eine **neue Sitzung** (in Claudian ein neuer Chat; im Terminal `/exit` und danach `claude` erneut). Damit prüfst du, ob Claude sich ohne Hinweis von dir an die Regeln hält.

7. **Claude:** Gib eine neue Woche und gib keinen Hinweis auf die Regeln:

   ```text
   Schreib den Wochenbericht für Woche 44. Erledigt: Kundentermin vorbereitet, Budget mit dem Team abgestimmt.
   ```

8. **Claude:** Frage nach den geladenen Regeln:

   ```text
   Welche CLAUDE.md-Dateien hast du gerade geladen? Nenn nur die Pfade.
   ```

   Claude nennt beide Dateien: die globale und die im Vault. Im Terminal zeigt `/memory` dasselbe.

**Platzhalter:** „Woche 44“ und die beiden Erledigt-Punkte sind Beispiele aus dem Video. Nimm deine eigene Wochennummer und deine eigenen Punkte.

## Das siehst du im Video

| Zeit | Szene |
|---|---|
| 00:00 | Einstieg: Regeln jedes Mal neu erklären ist mühsam, Titel „Teil 3: Die Hausordnung“ |
| 00:15 | Prinzip: `CLAUDE.md`, bei jedem Start gelesen |
| 00:27 | Zwei Ebenen: global und Projekt |
| 00:40 | Der Prompt für die globale Hausordnung, Claudes vier Fragen |
| 01:00 | Die beiden Aufträge noch einmal in Ruhe: links die globale Hausordnung, rechts die Projektregel |
| 01:11 | Ergebnis: eine kurze Datei, 25 Zeilen |
| 01:24 | Aus Fehlern: Wochenbericht mit leerem Abschnitt, Korrektur „Mach daraus eine Regel“, `CLAUDE.md` im Vault |
| 01:46 | Test: neue Sitzung, neue Woche, Frage nach den geladenen Dateien |
| 02:00 | Fertig, wenn …, Ausblick auf Teil 4 |

## Wenn es bei dir anders aussieht

- **Claude schreibt die globale Datei nach `~/.claude/CLAUDE.md`**, auch wenn du aus Claudian heraus arbeitest. Unter Windows liegt sie unter `%USERPROFILE%\.claude\CLAUDE.md`.
- **Die Fragen erscheinen als Auswahlfelder**, nicht als Text.
- **Deine Datei hat eine andere Zeilenzahl.** Der Prompt verlangt weniger als 40 Zeilen; das Video zeigt 25. Zu lang ist schlechter als zu kurz.
- **Dein Bericht hat keinen leeren Abschnitt.** Dann gibt es in Schritt 5 nichts zu streichen. Nimm eine andere Korrektur, die dich stört, und lass Claude daraus eine Regel machen.
- **`/memory` gibt es nur im Terminal.** In Claudian fragst du Claude (Schritt 8).
- **Claude bietet von sich aus eine Erinnerung für „freitags fertig“ an.** Das ist die Brücke zu Teil 11.
- **Globale und Projekt-Datei widersprechen sich.** Lass Claude eine Stelle entscheiden und die andere bereinigen.
- **Die Datei wird zu lang, Regeln gehen unter.** Kürzen statt ergänzen.
- **Passwörter oder Schlüssel gehören nie in die `CLAUDE.md`.** Dazu mehr in Teil 5.
- Der Befehl `/init` erzeugt einen ersten Entwurf einer Projekt-`CLAUDE.md`.

## Fertig, wenn …

- [ ] Auf „Welche CLAUDE.md-Dateien hast du geladen?“ nennt Claude deine globale Datei und die Projektdatei.
- [ ] In einer neuen Sitzung antwortet Claude im gewünschten Stil, ohne Hinweis von dir.
- [ ] Nach einer Korrektur hast du einmal „Mach daraus eine Regel“ gesagt.

## Wenn du hängst

```text
Ich komme bei Teil 3 (Hausordnung, CLAUDE.md) nicht weiter. Das passiert: [beschreibe, was du siehst]. Zeig mir, welche CLAUDE.md-Dateien du geladen hast, ob ihr Inhalt zusammenpasst und wo ich etwas ändern muss. Erklär es in einfachen Worten.
```

[Weiter: Teil 4 Das Kurzzeitgedächtnis](04-kurzzeitgedaechtnis.md)
