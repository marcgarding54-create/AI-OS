# Teil 9: Prüfen statt glauben

Ziel: „Fertig“ heißt bewiesen: Claude zeigt, dass es funktioniert, statt es zu behaupten. Dauer zum Mitmachen: ca. 45 Minuten. Voraussetzung: [Teil 8](08-projekte-planen.md).

## Video

{{VIDEO_09}}

Länge: 02:30

## Was du brauchst

- Die Dateien `KICKOFF.md` und `ENTSCHEIDUNGEN.md` aus Teil 8 und den Gegenleser aus Teil 7.
- Ein Terminal, in dem du Claude startest. Der eingebaute Befehl `/goal` zeigt seinen Prüfer nur dort (oder im Obsidian-Plugin „Terminal“ oder in VS Code). In Claudian läuft er auch, aber ohne Anzeige.
- Nichts zu installieren. Doku zu `/goal`: [code.claude.com/docs/en/goal](https://code.claude.com/docs/en/goal)

Geprüft wird nach Risiko:

| Stufe | Was | Wie geprüft |
|---|---|---|
| Kleines | Skripte, Notizen, Recherche, kleine Korrekturen | Claude führt aus und zeigt das Ergebnis |
| Was andere sehen oder nutzen | Veröffentlichungen, Mails an andere, Oberflächen | ein Helfer, der es nicht gebaut hat: der Tester prüft das Verhalten, der Gegenleser den Inhalt |

## Schritt für Schritt

1. **Claude:** Schreibe das als Regel in deine Hausordnung. Prompt in Claudian:

   ```text
   Füge in meine CLAUDE.md eine Regel „Prüfen nach Risiko“ ein: Kleine Aufgaben führst du aus und zeigst das Ergebnis. Für alles, was andere sehen oder nutzen, lässt du vor „fertig“ einen Agenten „tester“ das Verhalten prüfen (Oberflächen im Browser) und den „gegenleser“ den Inhalt. Melde nie „fertig“ ohne Beleg: Befehl, Ausgabe oder Screenshot.
   ```

   Der Auftrag besagt: Kleine Aufgaben zeigen ihr Ergebnis, alles andere prüfen Tester und Gegenleser, und „fertig“ gibt es nur mit Beleg.

2. **Claude:** Claude schlägt einen Agenten „tester“ vor. Antworte:

   ```text
   Ja, leg ihn an. Einen Browser braucht er erst, wenn wir eine Oberfläche bauen. Bis dahin reicht: ausführen und die Ausgabe zeigen.
   ```

   Claude legt den Tester an. Er führt Befehle wirklich aus und zeigt die echte Ausgabe. Ändern darf er nichts.

3. **Du:** Markiere im Bericht Woche 44 einen Stichpunkt mit `#privat`. Im Video: „Neues Notebook kaufen oder noch warten? #privat“. Der Mailtext soll diesen Punkt nicht enthalten.

4. **Du:** Öffne das Terminal im Ordner deines Vaults und starte Claude dort, damit du den Prüfer siehst.

   Mac:

   ```bash
   cd ~/wochenbericht
   ```

   Windows (PowerShell):

   ```powershell
   cd $HOME\wochenbericht
   ```

   Dann bei beiden:

   ```bash
   claude
   ```

   Alternativ geht das Obsidian-Plugin „Terminal“ oder VS Code; dort funktioniert es wie im Terminal.

5. **Claude:** Gib das Ziel. Schreibe in Claudes Eingabezeile (nicht ins normale Terminal):

   ```text
   /goal Die Datei „Mailentwurf Woche 44.md“ enthält den Mailtext für Woche 44 nach KICKOFF.md, Kriterien 4 bis 6: Betreff, knappe Einleitung, „Viele Grüße“, kein Punkt mit #privat. Der tester belegt das mit Befehl und Ausgabe. Oder Schluss nach 10 Runden.
   ```

   Ein guter `/goal`-Befehl hat drei Teile: **Bedingung** (was erfüllt sein muss), **Nachweis** (der tester belegt mit Befehl und Ausgabe) und **Obergrenze** (oder Schluss nach 10 Runden).

6. **Du:** Sieh zu. Unten rechts steht „◎ /goal active“. Claude schreibt den Entwurf und schickt den Tester los. Nach jeder Runde prüft ein zweites Modell, ob die Bedingung erfüllt ist. Der Tester belegt jedes Kriterium mit Befehl und Ausgabe, auch dass kein privater Punkt im Text steht. Erst dann meldet der Prüfer „✔ Goal achieved“. Claude sagt offen, was es nicht geprüft hat.

7. **Du:** Sieh dir bei „fertig“ den Beleg an: Befehl, Ausgabe oder Screenshot. Fehlt er, frag danach.

**Platzhalter:** „Mailentwurf Woche 44.md“ und „Woche 44“ sind Beispiele. „Kriterien 4 bis 6“ verweist auf die `KICKOFF.md` aus Teil 8. Schau in deiner Datei nach, welche Kriterien Betreff, Einleitung, Schluss und den Privat-Filter beschreiben, und setze deren Nummern ein.

## Das siehst du im Video

| Zeit | Szene |
|---|---|
| 00:00 | Einstieg: Claude sagt gern „fertig“, Titel „Teil 9: Prüfen statt glauben“ |
| 00:10 | Prinzip: Kleines ausführen und zeigen, Fremdes von einem Prüfer prüfen lassen |
| 00:21 | Die Regel: Prompt, `CLAUDE.md` mit „Prüfen nach Risiko“ |
| 00:36 | Der Regel-Prompt noch einmal in Ruhe: klein, was andere nutzen, nie fertig ohne Beleg |
| 00:50 | Der Tester wird angelegt |
| 01:01 | Erste Etappe: Mailtext für Woche 44, Kriterien 4 bis 6 aus `KICKOFF.md` |
| 01:14 | Der Befehl `/goal` im Terminal |
| 01:25 | Der `/goal`-Befehl noch einmal in Ruhe: Bedingung, Nachweis, Obergrenze |
| 01:36 | Es läuft: Entwurf, Tester, „/goal active“ |
| 01:48 | Erreicht: Belege je Kriterium, „Offen und ungeprüft“, „Goal achieved“ |
| 02:03 | In Claudian: `/goal` läuft, die Anzeige des Prüfers fehlt |
| 02:16 | Fertig, wenn …, Ausblick auf Teil 10 |

## Wenn es bei dir anders aussieht

- **`/goal` zeigt den Prüfer nur im Terminal.** In Claudian läuft der Befehl auch (das Sitzungsprotokoll meldet „Goal set“), aber die Anzeige „◎ /goal active“ und das Urteil fehlen. Im Terminal, im Obsidian-Plugin „Terminal“ und in VS Code sind beide sichtbar.
- **Der Prüfer führt selbst nichts aus.** Er urteilt nur über das, was im Gespräch sichtbar ist. Deshalb muss die Bedingung sagen, wie es bewiesen wird. Eine Obergrenze gehört hinein, sonst läuft es lange und verbraucht Kontingent.
- **`/goal` ohne Text zeigt den Stand, `/goal clear` bricht ab.** Die Bedingung darf bis zu 4.000 Zeichen lang sein.
- **Der Tester hat keinen Browser.** Claude legt ihn mit Read, Grep, Glob und Bash an. „Oberflächen meldet er als ungeprüft.“ Einen Browser braucht er erst, wenn du eine Oberfläche baust.
- **Im Video meldet der Prüfer nach 39 Sekunden und 1 Runde „Goal achieved“.** Bei dir kann es länger dauern.
- **Claude nennt offen, was ungeprüft blieb**, im Video die Kriterien 1 bis 3 und 7 bis 11. Das Prüfen nach Risiko heißt nicht, dass alles geprüft wird.
- **Ein Prüfer, der nur die Form prüft** (gibt es die Datei?), ist eine Fassade. Derselbe Agent soll nicht bauen und prüfen.
- **Der Befehl `cd` schlägt fehl:** Dein Ordner heißt anders oder liegt woanders. Frag Claudian nach dem Pfad des Vaults.

## Fertig, wenn …

- [ ] Claude nennt bei „fertig“ den Beleg.
- [ ] Du hast `/goal` einmal mit einer Bedingung samt Nachweis benutzt.
- [ ] Der Tester hat ein Ergebnis mit Befehl und Ausgabe belegt (bei Oberflächen: im Browser durchgeklickt).

## Wenn du hängst

```text
Ich komme bei Teil 9 (Prüfen nach Risiko, tester, /goal) nicht weiter. Das passiert: [beschreibe, was du siehst]. Prüf, ob die Regel „Prüfen nach Risiko“ in meiner CLAUDE.md steht und ob der Agent tester existiert. Hilf mir dann, einen /goal-Befehl mit Bedingung, Nachweis und Obergrenze für meine Aufgabe zu formulieren.
```

[Weiter: Teil 10 Die Knowledge Base](10-knowledge-base.md)
