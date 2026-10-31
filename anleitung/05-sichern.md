# Teil 5: Sichern

Ziel: Jede Änderung ist nachvollziehbar und liegt zusätzlich online. Schlüssel und Passwörter landen nie dort. Dauer zum Mitmachen: ca. 60 Minuten. Voraussetzung: [Teil 4](04-kurzzeitgedaechtnis.md).

## Video

{{VIDEO_05}}

Länge: 02:49

## Was du brauchst

Drei Werkzeuge und ein Konto, alle kostenlos:

| Werkzeug | Wofür | Link |
|---|---|---|
| **Git** | merkt sich jeden Stand deiner Dateien | [git-scm.com](https://git-scm.com) |
| **GitHub** (Konto) | Online-Ablage für deine Repos; private Repos sind im kostenlosen Plan enthalten | [github.com](https://github.com) |
| **GitHub CLI (`gh`)** | GitHub im Terminal bedienen, Claude benutzt es statt der Webseite | [cli.github.com](https://cli.github.com) |
| **gitleaks** | prüft vor dem Hochladen, ob Passwörter oder Schlüssel in den Dateien stehen | [github.com/gitleaks/gitleaks](https://github.com/gitleaks/gitleaks) |
| **Homebrew** (nur Mac) | installiert Programme mit einem Befehl | [brew.sh](https://brew.sh) |

Fünf Wörter reichen:

| Wort | Bedeutung |
|---|---|
| **Repo** | ein Ordner mit Verlauf |
| **Commit** | ein Speicherpunkt mit kurzer Beschreibung |
| **Push** | Speicherpunkte zu GitHub hochladen |
| **Pull** | den neuesten Stand herunterladen |
| **.gitignore** | Liste, was nie ins Repo darf |

Passwörter und Schlüssel stehen in einer eigenen Datei namens `.env`. Sie wird nie hochgeladen.

## Schritt für Schritt

1. **Du:** Lege ein GitHub-Konto an, falls du keines hast: Button „Sign up“ auf [github.com](https://github.com). Der kostenlose Plan reicht.

2. **Du:** Installiere die Werkzeuge. Öffne dafür das Terminal (Teil 1).

   **Mac.** Erst Git:

   ```bash
   xcode-select --install
   ```

   Dann Homebrew: Öffne [brew.sh](https://brew.sh), kopiere den Installationsbefehl von der Startseite und füge ihn ins Terminal ein. Danach die beiden Programme:

   ```bash
   brew install gh gitleaks
   ```

   **Windows (PowerShell).** Ein Befehl je Programm:

   ```powershell
   winget install --id Git.Git -e --source winget
   ```

   ```powershell
   winget install --id GitHub.cli --source winget
   ```

   ```powershell
   winget install Gitleaks.Gitleaks
   ```

3. **Du:** Öffne ein **neues** Terminal-Fenster (damit der Pfad stimmt) und melde dich einmal bei GitHub an. Das Terminal stellt Fragen und öffnet den Browser, dort bestätigst du die Anmeldung.

   ```bash
   gh auth login
   ```

4. **Claude:** Starte Claude in deinem Ordner (`cd wochenbericht`, dann `claude`; oder öffne Claudian in Obsidian). Gib den Auftrag:

   ```text
   Mach aus diesem Ordner ein privates Git-Repo und lade es mit gh auf GitHub hoch. Leg eine .gitignore an, die .env und alle Dateien mit Passwörtern ausschließt. Richte einen pre-push-Hook mit gitleaks ein, der das Hochladen stoppt, wenn ein Schlüssel gefunden wird. Ergänze meine CLAUDE.md um die Regeln: nach jedem abgeschlossenen Schritt committen und pushen, Schlüssel nur in .env, den Hook nie umgehen.
   ```

   Claude legt erst einen Plan vor und fragt nach: ob alles hochgeladen werden soll, wie das Repo heißt, wo die Regeln stehen sollen. Es bemerkt auch einen Widerspruch zu deiner Hausordnung, die Veröffentlichen ohne Rückfrage verbietet.

5. **Du:** Beantworte die Rückfragen und gib frei. Beispiel aus dem Video:

   ```text
   Go. Alles kommt hoch, das Repo ist privat. Der Push in dieses private Repo ist die Ausnahme, alles andere bleibt mit Rückfrage. Name: wochenbericht-demo. Die Regeln in die Projekt-CLAUDE.md.
   ```

   Claude legt das private Repo an, schreibt die `.gitignore`, richtet den Wächter (den Hook) ein und testet ihn mit einem falschen Schlüssel. Die neuen Regeln stehen in deiner `CLAUDE.md` (Abschnitt „Git & Sicherheit“).

6. **Du:** Spiele den Ernstfall durch. Schreibe eine **erfundene** Zeile, die wie ein Schlüssel aussieht, in `01 Inbox/Brain Dump.md`. Nie einen echten Schlüssel.

7. **Claude:** Bitte Claude zu speichern:

   ```text
   Ich hab was in den Brain Dump geschrieben. Speicher das bitte und lad es hoch.
   ```

   Claude prüft vorher mit gitleaks, findet den Schlüssel und lädt nichts hoch. Es schlägt vor, den Schlüssel in die `.env` zu verschieben, und fragt, bevor es deine Notiz ändert.

8. **Claude:** Gib frei:

   ```text
   Ja, mach es so. Den Token widerrufe ich selbst.
   ```

   Danach lädt Claude hoch. Einen echten Schlüssel erneuerst du beim Anbieter selbst.

9. **Claude:** Frage, was gespeichert ist:

   ```text
   Zeig mir als kurze Liste die Speicherpunkte bisher und ob das Repo auf GitHub privat ist.
   ```

   Du siehst die Speicherpunkte mit Beschreibung. Zusätzlich zeigt github.com das Repo mit dem Zeichen „Private“.

**Platzhalter:** `wochenbericht-demo` ist der Repo-Name im Video. Nimm einen eigenen Namen. Die Antwort in Schritt 5 hängt von Claudes Rückfragen ab; antworte in deinen Worten. Den „Schlüssel“ in Schritt 6 erfindest du. Schreibe nichts hinein, was du wirklich nutzt.

## Das siehst du im Video

| Zeit | Szene |
|---|---|
| 00:00 | Einstieg: Was, wenn etwas schiefgeht? Titel „Teil 5: Sichern“ |
| 00:14 | Prinzip: Git merkt sich jeden Stand, GitHub hält eine private Kopie, Schlüssel liegen in `.env` |
| 00:29 | Fünf Wörter: Repo, Commit, Push, Pull, .gitignore |
| 00:45 | Die drei Werkzeuge installieren, Befehle für Mac und Windows, einmal bei GitHub anmelden |
| 01:01 | Die Befehle noch einmal in Ruhe: links Mac, rechts Windows |
| 01:10 | Der Prompt, Claudes Plan mit „Vorher zu klären“ |
| 01:28 | Der Auftrag noch einmal in Ruhe, in vier Teilen |
| 01:35 | Antwort, privates Repo, `.gitignore`, Wächter getestet, neue Regeln in `CLAUDE.md` |
| 01:50 | Der Ernstfall: Schlüssel im Brain Dump, Claude lädt nichts hoch |
| 02:10 | Aufgeräumt: Schlüssel in die `.env`, Hinweiszeile im Brain Dump, Upload |
| 02:24 | Nachsehen: Liste der Speicherpunkte, Sichtbarkeit privat |
| 02:33 | Fertig, wenn …, Ausblick auf Teil 6 |

## Wenn es bei dir anders aussieht

- **Homebrew-Befehl.** Der genaue Installationsbefehl steht auf der Startseite von [brew.sh](https://brew.sh). Kopiere ihn von dort.
- **`xcode-select --install` öffnet ein Fenster von Apple** (**ungeprüft**, nicht in der Aufnahme). Bestätige die Installation und warte, bis sie fertig ist.
- **„Befehl nicht gefunden“ nach winget.** Öffne ein neues Terminal-Fenster.
- **gitleaks unter Windows.** `winget install Gitleaks.Gitleaks` ist ein Community-Paket und steht nicht in der gitleaks-Anleitung. Die offizielle Alternative: die ZIP-Datei von der [Releases-Seite](https://github.com/gitleaks/gitleaks/releases) entpacken und in den PATH legen.
- **`gh auth login` stellt mehrere Fragen.** Wähle GitHub.com und die Anmeldung über den Browser. Die genauen Auswahlpunkte sind **ungeprüft**.
- **Claude legt den Hook unter `.githooks/` an** und setzt `core.hooksPath`. Er testet ihn in einem Wegwerf-Repo. `git push` braucht den Credential-Helper von gh (`gh auth setup-git`); Claude setzt ihn selbst.
- **Claude fängt den Schlüssel schon vor dem Commit ab** (eigener gitleaks-Lauf). Der Hook ist die zweite Sicherung.
- **Claudian stellt Tabellen ohne Leerzeile davor roh dar.** Deshalb bittet der letzte Prompt um eine „kurze Liste“.
- **Ein einmal hochgeladener Schlüssel bleibt im Verlauf.** Erneuere ihn sofort beim Anbieter.
- **Schlüssel nicht in den Chat kopieren**, sondern selbst in die `.env` eintragen.
- **Wie der Hook unter Windows läuft** (er ist ein Skript, das Git ausführt), ist **ungeprüft**.

## Fertig, wenn …

- [ ] Das Repo liegt privat auf GitHub.
- [ ] Claude zeigt dir deine Speicherpunkte mit Beschreibung (im Terminal: `git log`).
- [ ] Beim Push meldet gitleaks „no leaks found“.
- [ ] Eine `.env` existiert und steht in der `.gitignore`.

## Wenn du hängst

```text
Ich komme bei Teil 5 (Git, GitHub, gitleaks, .env) nicht weiter. Ich habe [Mac oder Windows]. Das passiert: [beschreibe, was du siehst oder welche Meldung kommt]. Prüf, was installiert ist (git, gh, gitleaks) und ob ich bei GitHub angemeldet bin, und führ mich Schritt für Schritt zur Lösung. Füge keinen Schlüssel in den Chat ein.
```

[Weiter: Teil 6 Werkzeuge anbinden](06-werkzeuge-anbinden.md)
