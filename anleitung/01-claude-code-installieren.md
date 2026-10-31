# Teil 1: Claude Code installieren

Ziel: Claude Code läuft auf deinem Rechner und hat seine erste Aufgabe in einem Ordner erledigt. Dauer zum Mitmachen: ca. 30 Minuten. Voraussetzung: [Bevor du anfängst](00-bevor-du-anfaengst.md).

## Video

[Video ansehen (MP4, 17 MB)](https://github.com/marcgarding54-create/AI-OS/releases/download/v1.0/teil-01-claude-code-installieren.mp4)

Länge: 03:17

## Was du brauchst

- Ein Claude-Abo, mindestens **Pro**: 18 € im Monat, 15 € im Monat bei jährlicher Zahlung. Der kostenlose Plan enthält Claude Code nicht. [claude.com/pricing](https://claude.com/pricing)
- Mac mit macOS 13 oder neuer, oder Windows 10 (Version 1809) oder neuer. Zusatzsoftware ist nicht nötig.
- Offizielle Anleitung zur Installation: [code.claude.com/docs/en/setup](https://code.claude.com/docs/en/setup)
- Ohne Terminal geht es auch: der Code-Tab in der Claude-Desktop-App ([claude.com/download](https://claude.com/download)). Diese Anleitung nutzt das Terminal, weil dort alles genauso funktioniert und nichts versteckt ist.

## Schritt für Schritt

1. **Du:** Schließe ein Claude-Abo ab (mindestens Pro), falls du noch keines hast: [claude.com/pricing](https://claude.com/pricing). Die Preisseite zeigt 15 € bei jährlicher Zahlung und 18 € bei monatlicher.

2. **Du:** Öffne das Terminal.
   - Mac: `Cmd + Leertaste`, `Terminal` tippen, Enter.
   - Windows: Startmenü, `PowerShell` tippen, Enter.

3. **Du:** Füge den Installationsbefehl ein und drücke Enter. Dann wartest du, bis die Installation fertig ist.

   Mac (Terminal):

   ```bash
   curl -fsSL https://claude.ai/install.sh | bash
   ```

   Windows (PowerShell):

   ```powershell
   irm https://claude.ai/install.ps1 | iex
   ```

4. **Du:** Öffne ein **neues** Terminal-Fenster (das alte kennt den neuen Befehl noch nicht) und prüfe die Installation. Erscheint eine Versionsnummer, ist alles installiert.

   ```bash
   claude --version
   ```

5. **Du:** Lege einen Ordner für dein erstes Vorhaben an. Hier ist es ein Wochenbericht. Tippe die drei Befehle nacheinander, jeden mit Enter. Der erste legt den Ordner an, der zweite wechselt hinein, der dritte startet Claude in diesem Ordner.

   ```bash
   mkdir wochenbericht
   ```

   ```bash
   cd wochenbericht
   ```

   ```bash
   claude
   ```

   Die Befehle sind auf Mac und in der Windows-PowerShell gleich.

6. **Du:** Beim ersten Start fragt Claude nacheinander ein paar Dinge ab:
   - Farbschema: wähle eines.
   - Anmeldung: Der Browser öffnet sich. Melde dich mit deinem Claude-Konto an und klicke auf **Autorisieren**, wenn „Claude Code möchte eine Verbindung herstellen“ erscheint.
   - Ordner vertrauen: Claude fragt, ob es diesem Ordner vertrauen darf („Yes, I trust this folder“). Bestätige. Der Cursor steht zuerst auf „No, exit“, wähle „Yes“.

7. **Claude:** Gib die erste echte Aufgabe. Schreib den Prompt in Claudes Eingabezeile und drücke Enter.

   ```text
   Leg eine Datei woche-43 an und notier darin, was ich diese Woche erledigt habe: Präsentation fürs Team fertig, zwei Angebote verschickt, Urlaub eingetragen.
   ```

   Claude legt die Datei sofort an, denn eine neue Datei in deinem Ordner gilt als harmlos. Willst du jede Änderung selbst bestätigen, drück `Shift + Tab`, bis unten **manual mode** steht. Dann fragt Claude vorher, ob es darf.

8. **Du:** Öffne die Datei im Finder (Mac) oder im Explorer (Windows). Der Ordner `wochenbericht` liegt dort, wo das Terminal geöffnet war, auf dem Mac in deinem Benutzerordner (unter Windows ebenfalls, **ungeprüft**). Die Datei liegt wirklich auf deinem Rechner.

9. **Claude:** Ab hier gilt: Wenn du nicht weiterweißt, frag Claude. Zum Beispiel:

   ```text
   Ich bin neu bei Claude Code und habe noch nie mit dem Terminal gearbeitet. Erklär mir in einfachen Worten, was du in diesem Ordner tun kannst, was ein Terminal ist und wie ich dich sicher bediene. Frag mich danach, wofür ich dich nutzen möchte, und schlag mir drei erste Aufgaben vor.
   ```

   Claude erklärt sich selbst und schlägt Aufgaben vor, die zu dir passen.

10. **Du:** Merk dir zwei Tasten: `Esc` stoppt Claude mitten in der Arbeit. `/exit` beendet die Sitzung.

**Platzhalter:** `wochenbericht` und `woche-43` sind Beispiele. Nimm einen Ordnernamen, der zu deinem Vorhaben passt. Die Aufgabe in Schritt 7 kannst du mit deinen eigenen Erledigungen ausfüllen. In den späteren Teilen heißen Ordner und Datei weiter so wie im Video.

## Das siehst du im Video

| Zeit | Szene |
|---|---|
| 00:00 | Einstieg: Chat gegen Agent, Titel „Teil 1: Claude Code installieren“ |
| 00:17 | Prinzip: Claude Code arbeitet in einem Ordner, jede Aktion wird vorher geprüft |
| 00:34 | Abo: Preisseite, Pro markiert, 18 € monatlich und 15 € bei jährlicher Zahlung |
| 00:47 | Terminal öffnen: Mac über Spotlight, Windows über das Startmenü |
| 00:59 | Installationsbefehl einfügen und Enter |
| 01:14 | Der Befehl noch einmal in Ruhe: links Mac, rechts Windows |
| 01:23 | Prüfen mit `claude --version` im neuen Fenster |
| 01:33 | Ordner anlegen, Claude starten, im Browser anmelden, Ordner vertrauen |
| 01:53 | Erste Aufgabe, Claude legt `woche-43` an, die Datei im Finder |
| 02:33 | Ab jetzt fragen: der Prompt zum Fragen |
| 02:46 | Die beiden Aufträge noch einmal in Ruhe: erste Aufgabe und Prompt zum Fragen |
| 02:56 | Fertig, wenn …, Ausblick auf Teil 2 |

## Wenn es bei dir anders aussieht

- **Installation bricht ab mit „curl: (56) … 429“ (Mac).** Der Download-Server ist überlastet, nicht dein Rechner. Lass curl Fehler automatisch wiederholen und führe den Installationsbefehl aus Schritt 3 danach noch einmal aus. Die beiden Befehle schreiben zwei Zeilen in die Datei `~/.curlrc`:

  ```bash
  echo "retry = 10" >> ~/.curlrc
  ```

  ```bash
  echo "retry-all-errors" >> ~/.curlrc
  ```

  Beide Zeilen sind nötig: Das curl von macOS meldet den 429 sonst als Fehler 56, und den wiederholt `retry` allein nicht. Wenn du die Zeilen nicht dauerhaft willst, lösche sie danach aus `~/.curlrc` (oder bitte Claude darum). Unter Windows nutzt der Befehl `irm` statt curl. Ob dort derselbe Fehler auftritt, ist **ungeprüft**; wiederhole den Befehl dann später.
- **Am Ende der Installation steht ein Hinweis zum PATH (Mac).** Der Installer meldet dann, dass `~/.local/bin` nicht im PATH liegt, und druckt die passende Zeile für `~/.zshrc` gleich mit. Führe diese Zeile aus und öffne ein neues Fenster. Im Video ist dieser Hinweis nicht zu sehen; er kann auftreten.
- **„Befehl nicht gefunden“ bei `claude`.** Öffne ein neues Terminal-Fenster. Das alte kennt den Befehl noch nicht. Unter Windows nach der Installation ebenfalls ein neues PowerShell-Fenster.
- **Die Reihenfolge beim ersten Start weicht ab** (Farbschema, Anmeldung, Ordner vertrauen). Die Fragen sind dieselben. Welche Anmeldeart Claude anbietet, ist nicht überprüft: nimm das Claude-Konto mit Abo (**ungeprüft**).
- **Die Anmeldung klappt nicht.** Mit dem kostenlosen Claude-Plan geht es nicht, Claude Code braucht mindestens Pro.
- **Auf verwalteten Firmenrechnern kann die Installation gesperrt sein.** Wende dich dann an die IT oder nimm einen privaten Rechner.
- **Weitere Wege, wenn der Befehl nicht geht:**
  - Mac mit Homebrew: `brew install --cask claude-code` (lädt vom selben Server, hilft bei einem 429 also nicht).
  - Windows mit winget: `winget install Anthropic.ClaudeCode`.
  - Windows in der Eingabeaufforderung (CMD): `curl -fsSL https://claude.ai/install.cmd -o install.cmd && install.cmd && del install.cmd`.
  - Git for Windows ist optional. Ohne es nutzt Claude die PowerShell.
- **Bei dir fragt Claude vor einer neuen Datei um Erlaubnis.** Dann steht dein Modus auf „manual mode“. Mit `Shift + Tab` wechselst du zurück.
- **Claude zeigt englische Texte** („Do you want to create woche-43.md?“). Die Antworten sind: 1. Yes, 2. Yes, and switch to accept edits, 3. No.

## Fertig, wenn …

- [ ] `claude --version` zeigt eine Versionsnummer.
- [ ] Claude hat in deinem Ordner eine Datei angelegt, die du im Finder oder Explorer siehst.
- [ ] Du weißt, wie du Claude stoppst (`Esc`) und beendest (`/exit`).

## Wenn du hängst

Starte `claude` im Ordner `wochenbericht` und schreib:

```text
Ich komme bei Teil 1 (Claude Code installieren) nicht weiter. Ich habe einen [Mac oder Windows-Rechner]. Das passiert: [beschreibe, was du siehst oder welche Fehlermeldung kommt]. Erklär mir in einfachen Worten, was los ist, und führ mich Schritt für Schritt zur Lösung.
```

Läuft Claude noch nicht, öffne [claude.ai](https://claude.ai) im Browser und stell die Frage dort. Füge die Fehlermeldung als Text ein.

[Weiter: Teil 2 Der Arbeitsplatz](02-arbeitsplatz.md)
