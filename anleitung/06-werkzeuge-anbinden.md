# Teil 6: Werkzeuge anbinden

Ziel: Claude kann mehr als Dateien: Es holt die Termine der Woche aus deinem Kalender und schreibt sie in den Bericht. Dauer zum Mitmachen: ca. 45 Minuten. Voraussetzung: [Teil 5](05-sichern.md).

## Video

{{VIDEO_06}}

Länge: 02:17

## Was du brauchst

- Ein Google-Konto mit Kalender. Für Outlook gibt es den Connector **Microsoft 365**.
- Ein Claude-Konto mit dem Abo aus Teil 1. Connectoren sind in den Claude-Plänen enthalten.
- Einen Kalender, aus dem Claude Termine holen darf. Im Video ist es ein eigener Kalender namens „Demo“ mit erfundenen Terminen, damit kein echter Termin im Bild ist. Du kannst dir ebenfalls einen Testkalender anlegen.
- Nichts zu installieren. Anleitung zu den Google-Connectoren: [support.claude.com](https://support.claude.com/en/articles/10166901-use-google-workspace-connectors)

Es gibt zwei Arten von Werkzeugen:

| Art | Was es ist | Beispiele |
|---|---|---|
| **Kommandozeilen-Programme (CLI)** | Programme, die Claude im Terminal aufruft wie du | `git`, `gh` (Teil 5) |
| **MCP-Server** | kleine Adapter, die Claude die Werkzeuge eines Dienstes geben | Kalender, Browser, Dokumentation |

Kalender und Mail gehen am einfachsten über einen **Connector** in deinem Claude-Konto. Claude Code übernimmt die Verbindung von selbst.

## Schritt für Schritt

1. **Du:** Verbinde den Kalender, ohne Terminal. Öffne [claude.ai](https://claude.ai) im Browser und gehe auf **Anpassen** › **Connectoren** › **Google Calendar** › **Verbinden**. Melde dich bei Google an und erlaube den Zugriff. Die Seite erreichst du auch direkt: [claude.ai/customize/connectors](https://claude.ai/customize/connectors) (Anmeldung nötig).

2. **Du:** Trage im Kalender „Demo“ (oder deinem Testkalender) ein paar Termine für diese Woche ein, darunter einen privaten wie ein Mittagessen. Die Termine im Video sind erfunden.

3. **Du:** Starte Claude in deinem Ordner (Claudian in Obsidian oder `claude` im Terminal in `wochenbericht`). Eine **neue Sitzung** sieht die Connectoren deines Kontos.

4. **Claude:** Gib den Auftrag:

   ```text
   Hol dir die Termine dieser Woche aus meinem Google-Kalender „Demo“ und ergänze damit den Wochenbericht Woche 44. Nimm nur den Kalender „Demo“.
   ```

   Du siehst, was Claude tut: Es sucht das passende Werkzeug, fragt den Kalender ab und ergänzt den Bericht. Danach speichert es und lädt hoch, so wie es in deiner Hausordnung steht (Teil 5).

5. **Du:** Claude lässt einen privat wirkenden Termin weg und fragt nach, ob er hinein soll („Soll es auch hinein?“). Beantworte die Frage im nächsten Prompt.

6. **Claude:** Antworte und bitte um einen Ausblick:

   ```text
   Anna bleibt draußen. Nimm noch einen kurzen Ausblick auf die Termine nächster Woche auf.
   ```

   Kurz darauf steht der Abschnitt „Ausblick nächste Woche“ im Bericht.

**Platzhalter:**
- „Demo“ ist der Name deines Kalenders. Setze deinen ein.
- „Woche 44“ ist die Woche. Setze deine ein.
- „Anna“ ist die Person im privaten Termin (im Video „Mittagessen mit Anna“). Nimm den Namen deines privaten Termins oder lass den Satz so, wie Claude es nachfragt.

## Das siehst du im Video

| Zeit | Szene |
|---|---|
| 00:00 | Einstieg: Claude kennt nur, was im Ordner liegt, Titel „Teil 6: Werkzeuge anbinden“ |
| 00:11 | Prinzip: Kommandozeile (`gh`) und MCP-Server als Stecker zum Kalender |
| 00:30 | Verbinden: claude.ai › Anpassen › Connectoren › Google Calendar › Verbinden |
| 00:48 | Der Wochenbericht ohne Termine, der Auftrag |
| 00:58 | Der Auftrag noch einmal in Ruhe: Kalendername und Woche einsetzen |
| 01:09 | Claude im Einsatz: Werkzeug suchen, Kalender abfragen, Bericht ergänzen, speichern und hochladen |
| 01:21 | Ergebnis: vier Termine im Bericht, das Mittagessen fehlt mit Rückfrage |
| 01:31 | Antwort „Anna bleibt draußen“, Ausblick auf nächste Woche |
| 01:39 | Weniger ist mehr: 22 MCP-Server angeschlossen, 6 genutzt |
| 01:58 | Fertig, wenn …, Ausblick auf Teil 7 |

## Wenn es bei dir anders aussieht

- **Menünamen auf claude.ai.** Das Hilfe-Center nennt den Weg „Anpassen › Connectoren“. Die Seite verlangt eine Anmeldung und wurde nicht im Browser durchgeklickt (**ungeprüft**). Bei dir können die Namen leicht abweichen.
- **Claude sieht alle Connectoren deines Kontos, nicht nur den Kalender.** Auch Mail oder Drive, falls verbunden. Deshalb grenzt der Prompt mit „Nimm nur den Kalender „Demo““ ein. Claude hat sich im Video daran gehalten. Abschalten lassen sich Connectoren in Claude Code mit `"disableClaudeAiConnectors": true` in den Einstellungen ([Doku](https://code.claude.com/docs/en/mcp)).
- **Claude nennt dein angebundenes Konto** manchmal in Rückfragen, auch eine private Mailadresse. Denk daran, wenn du Bildschirmfotos teilst.
- **Claude speichert und lädt ohne Aufforderung hoch**, weil die Regel aus Teil 5 es verlangt.
- **Claude findet das Werkzeug selbst.** In Claudian siehst du es in der Liste der Schritte (Google Calendar, `list_calendars`, `list_events`).
- **Ein neu eingetragener MCP-Server** ist erst nach einem Neustart von Claude nutzbar.
- **Dein Kalender hat andere Termine**, deshalb auch andere Rückfragen. Der Ablauf ist derselbe.
- **Outlook statt Google:** nimm den Connector **Microsoft 365**.
- **Weniger ist mehr.** Jedes Werkzeug kostet bei jedem Start Aufmerksamkeit. Nimm eines dazu, wenn eine Aufgabe es verlangt.

### Zusätzlich: Browser und aktuelle Dokumentation (nicht im Video)

Die Langfassung zeigt noch zwei MCP-Server: Playwright (Claude bedient einen Browser) und Context7 (aktuelle Dokumentation). Sie kamen im Video nicht vor und sind hier **ungeprüft**. Sie brauchen [Node.js](https://nodejs.org/en/download) (LTS-Version), weil die Server über `npx` starten. Dieser Prompt in Claude:

```text
Ich möchte, dass du Webseiten im Browser testen und aktuelle Dokumentation nachschlagen kannst. Prüf, ob Node.js installiert ist, und hilf mir sonst bei der Installation. Richte dann die MCP-Server Playwright und Context7 ein. Sag mir, wann ich dich neu starten muss, und zeig mir danach mit /mcp, was verbunden ist.
```

Im Terminal zeigt `/mcp`, was verbunden ist; in Claudian frag Claude, welche Werkzeuge verbunden sind. Unter Windows braucht ein `npx`-Server manchmal den Umweg `cmd /c`; Claude kennt ihn.

## Fertig, wenn …

- [ ] Dein Kalender ist verbunden und Claude schreibt die Termine der Woche in den Bericht.
- [ ] Du kannst erklären, wann ein Programm für die Kommandozeile reicht und wann ein MCP-Server nötig ist.

## Wenn du hängst

```text
Ich komme bei Teil 6 (Werkzeuge anbinden, Kalender-Connector) nicht weiter. Das passiert: [beschreibe, was du siehst]. Zeig mir, welche Werkzeuge und Connectoren du gerade siehst, und prüf, ob der Kalender „Demo“ dabei ist. Erklär mir in einfachen Worten, was fehlt.
```

[Weiter: Teil 7 Rezepte und Rollen](07-rezepte-und-rollen.md)
