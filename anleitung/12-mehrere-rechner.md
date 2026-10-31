# Teil 12: Mehrere Rechner

Ziel: Dein System läuft auf einem zweiten Rechner, und eine Arbeit wechselt per Übergabe-Notiz das Gerät. Dauer zum Mitmachen: ca. 60 Minuten, plus Installation auf dem zweiten Rechner. Voraussetzung: [Teil 11](11-automationen.md), mindestens Teil 5.

## Video

{{VIDEO_12}}

Länge: 02:17

## Was du brauchst

- Das private Repo auf GitHub aus Teil 5, mit allem, was du bisher gebaut hast.
- Einen zweiten Rechner (Mac oder Windows), auf dem du Claude Code (Teil 1), Obsidian (Teil 2), Git und `gh` (Teil 5) installierst. Die Anleitung „Neuer Rechner“, die Claude in Schritt 1 schreibt, listet diese Schritte für dich auf.
- Dein GitHub-Konto.

Git ist die Brücke zwischen deinen Geräten: erst holen, dann arbeiten, dann hochladen. Wenn eine Arbeit das Gerät wechselt, schreibt Claude eine **Übergabe-Notiz**: Stand, nächster Schritt, offene Fragen, Belege.

## Schritt für Schritt

1. **Claude:** Auf dem ersten Rechner. Prompt in Claudian:

   ```text
   Ich will mein System auf einem zweiten Rechner nutzen, einem Mac im Büro. Prüf, ob alles Nötige in Git liegt und was nur auf diesem Rechner existiert. Schreib mir eine Anleitung „Neuer Rechner“ mit allen Installationsschritten und eine Vorlage für Übergabe-Notizen: Stand, nächster Schritt, offene Fragen, Belege.
   ```

   Der Auftrag besagt: prüfen, was in Git liegt und was nur hier; eine Anleitung für den neuen Rechner; eine Vorlage für Übergaben.

2. **Du:** Claude prüft genau. In Git liegen Notizen, Regeln, Hooks und sogar das Obsidian-Plugin. Nur auf diesem Rechner liegen deine Skills, die Agenten, die globale `CLAUDE.md`, die `.env` und die Anmeldungen. Ohne sie fehlt auf dem neuen Rechner die Hälfte. Claude schlägt vor, Skills und Agenten als Kopie ins Repo zu legen, und fragt drei Dinge, bevor es entscheidet.

3. **Claude:** Beantworte die Fragen und bitte um eine Übergabe-Notiz. Beispiel aus dem Video (die Antworten hängen von Claudes Fragen ab):

   ```text
   Go. 1. Ja, leg den Ordner config an. 2. Ändere das Skript, damit es ohne flock läuft. 3. Committe alle drei. Schreib danach eine Übergabe-Notiz für den Mail-Entwurf, ich mache morgen am Mac im Büro weiter.
   ```

   Heraus kommen die Anleitung „Neuer Rechner“ (geprüft von Tester und Gegenleser) und eine Übergabe-Notiz mit Stand, nächstem Schritt, offenen Fragen und Belegen. Zum Schluss schlägt Claude neue Notizen für die Knowledge Base vor.

4. **Du:** Auf dem zweiten Rechner: Installiere zuerst die Programme laut der Anleitung „Neuer Rechner“ (Claude Code, Obsidian mit Claudian, Git, `gh`, bei Bedarf gitleaks). Melde dich bei Claude an (Teil 1).

5. **Du:** Melde dich im Terminal bei GitHub an und richte Git für den Zugang ein.

   ```bash
   gh auth login
   ```

   ```bash
   gh auth setup-git
   ```

6. **Du:** Hole das Repo von GitHub.

   Mac (Terminal):

   ```bash
   git clone https://github.com/<konto>/<repo>.git ~/wochenbericht
   ```

   Windows (PowerShell, Schreibweise des Zielordners **ungeprüft**):

   ```powershell
   git clone https://github.com/<konto>/<repo>.git $HOME\wochenbericht
   ```

7. **Du:** Wechsle in den Ordner und schalte die Hooks des Repos ein.

   Mac:

   ```bash
   cd ~/wochenbericht
   ```

   Windows:

   ```powershell
   cd $HOME\wochenbericht
   ```

   Danach bei beiden:

   ```bash
   git config core.hooksPath .githooks
   ```

8. **Du:** Öffne Obsidian und wähle **Ordner als Vault öffnen**, dann den Ordner `wochenbericht`. Obsidian fragt „Vertraust du dem Ersteller dieses Vaults?“. Claudian ist sofort da, weil auch das Plugin im Repo liegt.

9. **Claude:** Starte Claudian (Modell wählen wie in Teil 2, falls nötig) und schreibe:

   ```text
   Mach da weiter, wo ich am anderen Rechner aufgehört habe.
   ```

   Claude liest die Übergabe-Notiz, prüft jeden Beleg nach und sagt dir, was als Nächstes an dir liegt.

**Platzhalter:**
- `<konto>` ist dein GitHub-Benutzername. `<repo>` ist der Repo-Name aus Teil 5 (im Video `wochenbericht-demo`).
- „einem Mac im Büro“ ersetzt du durch „einem Windows-Rechner“ oder dein Gerät.
- „Mail-Entwurf“ in Schritt 3 ist die Arbeit aus Teil 8 und 9. Nimm deinen Strang.
- Der Ordner `config` und die Frage zu `flock` stammen aus Claudes Fragen im Video. Bei dir stellt Claude andere.

## Das siehst du im Video

| Zeit | Szene |
|---|---|
| 00:00 | Einstieg: Was, wenn du im Büro weitermachen willst, Titel „Teil 12: Mehrere Rechner“ |
| 00:12 | Prinzip: Git als Brücke, holen, arbeiten, hochladen; die Übergabe-Notiz |
| 00:24 | Der Auftrag an Claude |
| 00:31 | Der Prompt noch einmal in Ruhe |
| 00:45 | Was mitkommt (in Git) und was nur auf diesem Rechner liegt |
| 01:02 | Drei Entscheidungen, Antwort und Bitte um eine Übergabe-Notiz |
| 01:15 | Anleitung „Neuer Rechner“ und Übergabe-Notiz, Vorschläge für die Knowledge Base |
| 01:31 | Zweiter Rechner: `git clone`, `git config core.hooksPath .githooks`, Vertrauensdialog in Obsidian |
| 01:45 | Weitermachen: „Mach da weiter, wo ich am anderen Rechner aufgehört habe.“ |
| 02:01 | Fertig, wenn …, alle zwölf Teile |

## Wenn es bei dir anders aussieht

- **Der zweite Rechner im Video ist ein frisch aufgesetzter Testrechner unter Linux, kein Mac.** Claude erkennt das und sagt es („Diese Sitzung läuft unter Linux“). Die Schritte sind dieselben. Auf einem echten Mac oder Windows-Rechner kommen die Installationen aus der Anleitung „Neuer Rechner“ dazu.
- **Mac-Stolpersteine, die Claude selbst fand:** `flock` fehlt unter macOS, und Obsidian erbt den Homebrew-PATH nicht.
- **Auf dem zweiten Rechner reichen** `gh auth setup-git`, `git clone` und `core.hooksPath`. Claudian war im Video sofort aktiv.
- **Nicht in Git:** Skills und Agenten (`~/.claude/`), die globale `CLAUDE.md`, `core.hooksPath`, die `.env`, Anmeldungen und die Programme. Trage Schlüssel und `.env` selbst auf dem neuen Rechner ein. Nimm sie nie in Git auf.
- **Große Dateien gehören nicht in Git.** Sie machen jedes Repo langsam. Die Langfassung nennt dafür einen eigenen Speicher.
- **Zwei Geräte ändern gleichzeitig dieselbe Datei:** erst holen (pull), dann arbeiten.
- **Der Hook (Teil 5) unter Windows** ist ein Skript. Ob `git config core.hooksPath .githooks` dort ohne Anpassung funktioniert, ist **ungeprüft**.

## Fertig, wenn …

- [ ] Auf dem zweiten Gerät startet Claude mit deinen Regeln und deinem Übertrag.
- [ ] Eine Übergabe-Notiz hat einen Strang sauber übergeben.

Damit hast du alle zwölf Teile. Ab hier gilt, was von Anfang an galt: Frag Claude.

## Wenn du hängst

```text
Ich komme bei Teil 12 (zweiter Rechner, Übergabe-Notiz) nicht weiter. Mein zweiter Rechner ist [Mac oder Windows]. Das passiert: [beschreibe, was du siehst]. Prüf, was auf diesem Rechner fehlt (Programme, Anmeldungen, .env, Skills und Agenten), vergleiche es mit der Anleitung „Neuer Rechner“ und führ mich Schritt für Schritt zur Lösung.
```

[Weiter: Teil 13, Was du damit bauen kannst](13-was-du-damit-bauen-kannst.md)
