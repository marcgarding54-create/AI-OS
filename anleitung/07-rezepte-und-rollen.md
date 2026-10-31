# Teil 7: Rezepte und Rollen

Ziel: Ein wiederkehrender Ablauf ist als Rezept gespeichert, und Claude gibt Teilarbeit an einen Helfer mit eigener Rolle ab. Dauer zum Mitmachen: ca. 45 Minuten. Voraussetzung: [Teil 6](06-werkzeuge-anbinden.md) (der Skill im Video nutzt den Kalender aus Teil 6; ohne Kalender reicht Teil 3).

## Video

{{VIDEO_07}}

Länge: 03:02

## Was du brauchst

- Den Wochenbericht aus den früheren Teilen und, wenn du den Kalender nutzt, die Anbindung aus Teil 6.
- Nichts zu installieren. Zum Nachlesen: [Skills](https://code.claude.com/docs/en/skills), [Subagenten](https://code.claude.com/docs/en/sub-agents)

Zwei Begriffe:

| Begriff | Was es ist | Wo es liegt |
|---|---|---|
| **Skill** | ein Rezept: eine Datei `SKILL.md` mit den Schritten eines Ablaufs. Oben steht, wann er greift. | `~/.claude/skills/<name>/SKILL.md` (Windows: `%USERPROFILE%\.claude\skills\<name>\SKILL.md`) |
| **Agent** | eine Rolle: ein zweiter Claude mit eigenem Auftrag, der nur liest, was er braucht, und ein Ergebnis zurückmeldet | `~/.claude/agents/<name>.md` (Windows: `%USERPROFILE%\.claude\agents\<name>.md`) |

## Schritt für Schritt

1. **Claude:** Beschreibe deinen Ablauf in ein paar Sätzen und lass daraus einen Skill und einen Agenten machen. Schreib den Prompt:

   ```text
   Ich beschreibe dir einen Ablauf, den ich jeden Freitag mache: Ich hole die Termine der Woche aus meinem Kalender „Demo“, nehme Erledigtes und Offenes aus den Tagesnotizen der Woche und schreibe daraus den Wochenbericht nach den Regeln in der CLAUDE.md. Mach daraus einen Skill in ~/.claude/skills/ mit einer Beschreibung, die sagt, wann du ihn nutzen sollst. Leg außerdem einen Agenten „gegenleser“ an, der Ergebnisse kritisch prüft, Fehler mit Fundstelle nennt und nichts selbst ändert.
   ```

   Der Auftrag hat drei Teile: (1) dein Ablauf in ein paar Sätzen, (2) „Mach daraus einen Skill, mit einer Beschreibung, wann er greifen soll“, (3) „Leg einen Agenten an, der prüft und nichts ändert“. Genau so legst du jeden anderen Skill an, zum Beispiel für Angebote oder Protokolle.

2. **Du:** Claude legt beide Dateien an: `~/.claude/skills/wochenbericht/SKILL.md` und `~/.claude/agents/gegenleser.md`. Der Skill beschreibt jeden Schritt bis zum Speichern. Der Gegenleser darf nur lesen (Read, Grep, Glob), ändern kann er technisch gar nicht. Claude sagt ehrlich, dass beides noch ungeprüft ist.

3. **Claude:** Starte eine **neue Sitzung** und gib nur das Stichwort:

   ```text
   Schreib den Wochenbericht für diese Woche.
   ```

   Claude lädt den Skill von selbst und arbeitet ihn Schritt für Schritt ab: Datum, Kalender, Tagesnotizen. In der Liste der Schritte steht „Skill wochenbericht“. Weil der Bericht schon existiert, überschreibt Claude nichts und macht einen Vorschlag mit Rückfragen.

4. **Claude:** Gib frei und lass den Gegenleser prüfen:

   ```text
   Aktualisier ihn. Die zwei erledigten Punkte stimmen, Anna bleibt draußen, Offen bitte ergänzen.
   ```

   Claude ändert den Bericht und schickt den Gegenleser los („Wochenbericht 44 gegenlesen“). Der prüft mit frischem Blick gegen Regeln und Quellen und meldet einen Fund. Claude wägt ab, erklärt, was es damit tut, und speichert und lädt erst danach hoch.

**Platzhalter:** „Demo“ ist der Kalendername, „Anna“ der private Termin und „die zwei erledigten Punkte“ beziehen sich auf den Vorschlag im Video. Setze deine eigenen Angaben ein; Claude schlägt dir Punkte vor, auf die du antwortest. „Woche 44“ steht im Namen des Prüfauftrags und ist ein Beispiel.

## Das siehst du im Video

| Zeit | Szene |
|---|---|
| 00:00 | Einstieg: Jeden Freitag dasselbe erklären, Titel „Teil 7: Rezepte und Rollen“ |
| 00:14 | Prinzip: Skill ist ein Rezept, Agent ist eine Rolle |
| 00:31 | Der Auftrag an Claude: Skill und Agent „Gegenleser“ |
| 00:45 | Claude legt beide Dateien an |
| 00:55 | Das Rezept zum Mitnehmen: der Auftrag in drei Teilen noch einmal in Ruhe |
| 01:24 | Neue Sitzung, Claude lädt den Skill und arbeitet ihn ab |
| 01:37 | Vorschlag statt Überschreiben, das Mittagessen wird wieder vorgeschlagen |
| 01:53 | Freigabe, der Gegenleser läuft und meldet einen Fund |
| 02:08 | Was ein Subagent ist: zweiter Claude mit einem Auftrag, frischem Blick, nur lesend |
| 02:36 | Ergebnis: Bericht mit Abschnitt „Offen“, aktualisiert, committet und gepusht |
| 02:44 | Fertig, wenn …, Ausblick auf Teil 8 |

## Wenn es bei dir anders aussieht

- **Claude schreibt Skill und Agent ohne vorherigen Plan** (kleine Aufgabe) und sagt, dass beides ungeprüft ist.
- **In der neuen Sitzung lädt Claudian den Skill sichtbar** („Skill wochenbericht“), ohne dass du `/wochenbericht` tippst. Im Terminal listet `/skills` alle Skills.
- **Das Mittagessen taucht wieder auf.** Eine neue Sitzung kennt das Gespräch von vorhin nicht. Was dauerhaft gelten soll, gehört in eine Datei (`CLAUDE.md`, Skill oder Knowledge Base). Teil 10 zeigt, wie Claude so etwas dauerhaft lernt.
- **Der Fund des Gegenlesers fällt schwach aus**, und Claude begründet, warum es nichts ändert. Das ist die Aufgabe des Gegenlesers: finden, nicht ändern.
- **Ein Agent existiert erst, wenn seine Datei in `~/.claude/agents` liegt**, nicht wenn er irgendwo beschrieben ist.
- **Der Skill greift nie oder ständig.** Die Beschreibung ist zu vage („hilft bei Texten“). Sie muss sagen, wann der Skill gelten soll.
- **Zu viele Skills.** Claude wählt schlechter. Wenige gute Rezepte schlagen viele mittelmäßige.
- **Du hast keinen Kalender angebunden.** Nimm im Prompt den Satz zum Kalender heraus.

## Fertig, wenn …

- [ ] Dein Skill erscheint in der Liste der Schritte, wenn du den Auslöser nennst (im Terminal zeigt `/skills` alle).
- [ ] Der Gegenleser hat ein Ergebnis einmal geprüft und etwas gefunden.

## Wenn du hängst

```text
Ich komme bei Teil 7 (Skill und Agent) nicht weiter. Das passiert: [beschreibe, was du siehst]. Zeig mir, welche Skills in ~/.claude/skills und welche Agenten in ~/.claude/agents liegen, ob ihre Beschreibung sagt, wann sie greifen, und was ich ändern muss, damit „Schreib den Wochenbericht für diese Woche.“ den Skill auslöst.
```

[Weiter: Teil 8 Projekte planen](08-projekte-planen.md)
