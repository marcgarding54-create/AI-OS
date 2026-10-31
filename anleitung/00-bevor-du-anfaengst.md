# Bevor du anfängst

Diese Seiten gehören zur Videoreihe „AI OS Teil 1: Vom Chat zum KI-Betriebssystem“. Es gibt dreizehn Videos und zu jedem eine Seite. Du liest die Seite, schaust das Video und machst jeden Schritt mit Claude nach. Du musst dafür nie im Terminal getippt haben.

Diese Seite erklärt, was du vorher wissen musst. Sie dauert etwa 10 Minuten.

## So sind die Seiten aufgebaut

- **Du:** Das kannst nur du tun: ein Konto anlegen, dich anmelden, in Obsidian klicken, einen Connector freischalten.
- **Claude:** Du gibst Claude einen Auftrag (einen Prompt), Claude erledigt den Rest.
- Jeder Befehl und jeder Prompt steht in einem eigenen Kasten. Oben rechts im Kasten erscheint ein Kopierknopf: ein Klick, und der Text liegt in der Zwischenablage.
- Mac und Windows stehen getrennt, wo sie sich unterscheiden. Steht nichts dabei, gilt es für beide.
- Platzhalter (zum Beispiel Kalendername „Demo“ oder „Woche 44“) erklärt ein Hinweis unter dem Kasten.
- Was bei den Aufnahmen nicht geprüft werden konnte (zum Beispiel manche Schritte unter Windows), ist mit **ungeprüft** markiert.

Die Teile bauen aufeinander auf. Als durchgehendes Beispiel entsteht ein persönlicher **Wochenbericht**: Teil 1 legt den Ordner `wochenbericht` an, die späteren Teile erweitern ihn Schritt für Schritt.

## Was du brauchst

- Einen Mac (macOS 13 oder neuer) oder einen Windows-Rechner (Windows 10, Version 1809 oder neuer).
- Ein Claude-Abo, **mindestens Pro**: 18 € im Monat, 15 € im Monat bei jährlicher Zahlung. Im kostenlosen Plan ist Claude Code nicht enthalten. Preise: [claude.com/pricing](https://claude.com/pricing)
- Einen Internetzugang und etwa 30 bis 60 Minuten je Teil.

## Das Terminal öffnen

Das Terminal ist ein Fenster, in das du Befehle tippst. Du brauchst es für den ersten Teil und ab und zu danach.

**Mac:** Drücke `Cmd + Leertaste`. Es öffnet sich die Spotlight-Suche. Tippe `Terminal` und drücke Enter.

**Windows:** Öffne das Startmenü, tippe `PowerShell` und drücke Enter. Nimm **PowerShell**, nicht die Eingabeaufforderung (CMD).

Es erscheint ein Fenster mit einer Eingabezeile. Dort tippst du oder fügst Befehle ein.

## Kopieren und Einfügen

| | Mac | Windows |
|---|---|---|
| Kopieren | `Cmd + C` | `Strg + C` |
| Einfügen | `Cmd + V` (auch im Terminal) | `Strg + V`, in PowerShell auch ein Rechtsklick |

Einfacher: der Kopierknopf oben rechts im Kasten.

**Enter** schickt ab. Ein eingefügter Befehl läuft erst, wenn du Enter drückst.

## Befehle und Prompts

Es gibt zwei Arten von Kästen.

**Befehle** tippst oder fügst du ins Terminal ein. Sie sind als `bash` (Mac) oder `powershell` (Windows) gekennzeichnet:

```bash
claude --version
```

**Prompts** sind Texte, die du an Claude schreibst, so wie du einer Person einen Auftrag gibst. Du schreibst sie, nachdem Claude gestartet ist: im Terminal nach dem Befehl `claude`, ab Teil 2 auch in Obsidian im Fenster von Claudian. Sie sind als `text` gekennzeichnet:

```text
Erklär mir in einfachen Worten, was du in diesem Ordner tun kannst.
```

Wichtig: Einen Prompt fügst du nicht in die normale Terminal-Eingabe ein, sondern erst, wenn Claude läuft. Ein Befehl gehört ins Terminal, ein Prompt zu Claude.

## Was Claude Code ist

Claude Code ist ein Agent, kein Chat. Er arbeitet in einem **Ordner** auf deinem Rechner, liest und schreibt dort Dateien und führt Befehle aus. Du startest ihn mit dem Befehl `claude`. Alles, was Claude tut, landet als Datei in diesem Ordner. Du kannst es sehen, ändern und löschen.

## Der Auto-Modus

Claude Code startet im **Auto-Modus** (seit Version 2.1.283). Ein zweites Modell prüft jede Aktion: Harmloses erledigt Claude selbst, zum Beispiel eine neue Datei im Ordner anlegen. Riskantes wird blockiert.

Willst du jede Änderung selbst bestätigen, drück `Shift + Tab`, bis unten **manual mode** steht. Dann fragt Claude vor jeder Änderung, ob es darf.

## Hilfe holen

Sobald Claude Code installiert ist (Teil 1), kannst du Claude jederzeit fragen, auch zu den Teilen, die noch kommen. Jede Seite endet mit einem Prompt für genau diesen Teil. Ein allgemeiner Prompt:

```text
Ich bin neu bei Claude Code und habe noch nie mit dem Terminal gearbeitet. Erklär mir in einfachen Worten, was du in diesem Ordner tun kannst, was ein Terminal ist und wie ich dich sicher bediene. Frag mich danach, wofür ich dich nutzen möchte, und schlag mir drei erste Aufgaben vor.
```

## Die zwölf Teile

| Teil | Titel | Ergebnis |
|---|---|---|
| 1 | [Claude Code installieren](01-claude-code-installieren.md) | Claude läuft und legt die erste Datei an |
| 2 | [Der Arbeitsplatz](02-arbeitsplatz.md) | Obsidian und Claude nebeneinander |
| 3 | [Die Hausordnung](03-hausordnung.md) | Claude kennt deine Regeln bei jedem Start |
| 4 | [Das Kurzzeitgedächtnis](04-kurzzeitgedaechtnis.md) | Brain Dump, Tagesnotiz, Übertrag |
| 5 | [Sichern](05-sichern.md) | Git, GitHub, gitleaks, `.env` |
| 6 | [Werkzeuge anbinden](06-werkzeuge-anbinden.md) | Kalender per Connector |
| 7 | [Rezepte und Rollen](07-rezepte-und-rollen.md) | Skill und Agent |
| 8 | [Projekte planen](08-projekte-planen.md) | Ausfragen, KICKOFF.md, ENTSCHEIDUNGEN.md |
| 9 | [Prüfen statt glauben](09-pruefen-statt-glauben.md) | Beleg statt Behauptung, `/goal` |
| 10 | [Die Knowledge Base](10-knowledge-base.md) | Lektionen, die bleiben |
| 11 | [Automationen](11-automationen.md) | Hook und geplante Aufgabe |
| 12 | [Mehrere Rechner](12-mehrere-rechner.md) | Umzug auf einen zweiten Rechner |

[Weiter: Teil 1 Claude Code installieren](01-claude-code-installieren.md)
