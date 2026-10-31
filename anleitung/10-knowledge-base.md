# Teil 10: Die Knowledge Base

Ziel: Was du einmal gelernt hast, findet Claude wieder, in jedem Projekt. Dauer zum Mitmachen: ca. 45 Minuten. Voraussetzung: [Teil 9](09-pruefen-statt-glauben.md) (mindestens Teil 5).

## Video

{{VIDEO_10}}

Länge: 02:23

## Was du brauchst

- Den Wochenbericht-Skill aus Teil 7. Das Video knüpft an dessen Fehler an: Eine neue Sitzung hat das gestrichene Mittagessen wieder vorgeschlagen.
- Nichts zu installieren.

Es gibt zwei Gedächtnisse:

| Gedächtnis | Wofür | Lebensdauer |
|---|---|---|
| **Akte** | gehört zum Projekt: Was ist beschlossen, was kommt als Nächstes | wird abgeschlossen und archiviert |
| **Handbuch** (die Knowledge Base) | nach Themen sortiert, hilft in jedem Projekt | lebt weiter |

Die Prüffrage beim Ablegen: **Hilft das auch woanders?** Dann gehört es in die Knowledge Base. Projektstände gehören nicht hinein.

Eine Notiz hat immer denselben Aufbau: Der **Titel ist die Aussage** (wer nur die Titel liest, kennt schon die Lektionen), dazu `laden_wenn` (in welcher Lage die Notiz wichtig ist), Kontext (ein bis vier Sätze), Erkenntnis, Details.

## Schritt für Schritt

1. **Claude:** Lege die Knowledge Base an. Prompt in Claudian:

   ```text
   Leg einen Ordner „05 Knowledge Base“ an, mit Unterordnern für vier bis sechs Themen, die zu meiner Arbeit passen (frag mich danach). Schreib eine Vorlage für eine Notiz: Titel ist die Aussage, dann laden_wenn, Kontext, Erkenntnis, Details. Ergänze meine CLAUDE.md: Vor jeder größeren Aufgabe suchst du dort, und am Ende jeder Etappe schlägst du mir neue Notizen vor. Projektstände gehören nicht hinein, nur was auch woanders hilft.
   ```

   Der Auftrag hat vier Teile: ein Ordner mit deinen Themen (frag mich), eine Vorlage, in der der Titel die Aussage ist, zwei Regeln (vorher nachschlagen, nachher Neues vorschlagen), und: keine Projektstände.

2. **Du:** Claude fragt per Auswahl, welche Themen zu deiner Arbeit passen, und schlägt selbst welche vor (ein zweiter Reiter zeigt „Mehr Themen“). Wähle aus. Claude legt `05 Knowledge Base/` mit je einem Unterordner pro Thema an, dazu die Datei `Vorlage Wissensnotiz.md`, und ergänzt die `CLAUDE.md` um den Abschnitt „Knowledge Base“.

3. **Claude:** Gib die erste Lektion. Erzähle einen Fehler aus deiner Arbeit:

   ```text
   Eine erste Notiz: Beim Wochenbericht hast du zweimal das „Mittagessen mit Anna“ vorgeschlagen, obwohl ich es schon einmal rausgenommen hatte. Private Termine gehören nicht in einen Bericht fürs Team. Mach daraus eine Notiz.
   ```

   Claude macht daraus eine kurze Notiz, deren Titel die Aussage ist („Private Termine gehören nicht in einen Bericht fürs Team“). Den Namen Anna lässt es weg, damit die Notiz auch bei anderen Berichten hilft.

4. **Du:** Öffne die Notiz in Obsidian. Du erkennst Titel, `laden_wenn` und Erkenntnis.

5. **Claude:** Starte eine **neue Sitzung** und gib denselben Auftrag wie in Teil 7:

   ```text
   Schreib den Wochenbericht für diese Woche.
   ```

   Claude lädt den Skill und liest als Erstes die passende Notiz aus der Knowledge Base. Diesmal steht das Mittagessen nicht im Vorschlag, und Claude sagt auch, warum. Es findet sogar einen zweiten privaten Punkt und fragt nach, statt zu raten.

**Platzhalter:** Der Prompt in Schritt 3 beschreibt das Video-Beispiel („Mittagessen mit Anna“). Setze deine eigene Erfahrung ein: Wo hat Claude etwas wiederholt, das du schon korrigiert hattest? „Anna“ ist erfunden.

## Das siehst du im Video

| Zeit | Szene |
|---|---|
| 00:00 | Einstieg: Das Mittagessen aus Teil 7 kam wieder, Titel „Teil 10: Die Knowledge Base“ |
| 00:14 | Prinzip: Akte und Handbuch, die Prüffrage „Hilft das auch woanders?“ |
| 00:30 | Der Prompt, Claude fragt die Themen |
| 00:40 | Der Prompt noch einmal in Ruhe: Ordner mit Themen, Vorlage, zwei Regeln, keine Projektstände |
| 00:59 | Ordner, Vorlage und die zwei Regeln in der `CLAUDE.md` |
| 01:16 | Die erste Lektion: Claude macht aus dem Fehler eine Notiz |
| 01:33 | Anatomie einer Notiz: Titel, `laden_wenn`, Erkenntnis |
| 01:44 | Der Test: neue Sitzung, Claude liest erst die Notiz |
| 01:54 | Gelernt: Das Mittagessen steht zu Recht nicht drin |
| 02:07 | Fertig, wenn …, Ausblick auf Teil 11 |

## Wenn es bei dir anders aussieht

- **Jeder Themenordner enthält eine leere Platzhalterdatei** (`.gitkeep`), damit Git ihn mitnimmt. Das ist normal. Im Video waren es fünf Themenordner.
- **Neue Notizen schlägt Claude vor und legt sie nach deiner Freigabe an.** Claude ergänzt die `CLAUDE.md` so: vor größeren Aufgaben suchen und genutzte Notizen nennen; neue Notizen nur nach Freigabe; keine Projektstände, Termine, Kundendaten.
- **Claude verallgemeinert die Lektion selbst** („Mittagessen mit einer Person“) und bietet an, den Skill um einen Filter zu ergänzen. Antworte darauf mit Ja oder Nein.
- **Die Themen und die Notiz sehen bei dir anders aus.** Der Aufbau bleibt gleich.
- **Zwei Aussagen in einer Notiz:** besser zwei Notizen.
- **Projektstände im Handbuch** gehören in die Akte.
- **Notizen nie ergänzen, nur neu anlegen:** Dubletten widersprechen sich irgendwann. Bitte Claude, vor dem Anlegen zu suchen, ob es die Aussage schon gibt.
- **Kundendaten nie roh**, nur anonymisiert.
- **Suchindex.** Ein Index, der nach Bedeutung sucht, lohnt sich erst ab einigen hundert Notizen. Am Anfang findet Claude Notizen über Dateinamen und Volltextsuche. Die Notizen bleiben Textdateien; fällt ein Index weg, ist nichts verloren.
- **Klein anfangen:** Ein Ordner reicht.

## Fertig, wenn …

- [ ] Die ersten drei Notizen existieren, jede mit einer Aussage im Titel.
- [ ] Auf „Was wissen wir über …?“ findet Claude die passende Notiz.
- [ ] Deine Hausordnung verlangt Nachschlagen vor größeren Aufgaben.

## Wenn du hängst

```text
Ich komme bei Teil 10 (Knowledge Base) nicht weiter. Das passiert: [beschreibe, was du siehst]. Zeig mir, welche Ordner und Notizen in „05 Knowledge Base“ liegen und ob meine CLAUDE.md das Nachschlagen verlangt. Hilf mir dann, aus [einem Fehler, der mir aufgefallen ist] eine Notiz zu machen, deren Titel die Aussage ist.
```

[Weiter: Teil 11 Automationen](11-automationen.md)
