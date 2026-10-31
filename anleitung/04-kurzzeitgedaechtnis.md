# Teil 4: Das Kurzzeitgedächtnis

Ziel: Jede Sitzung beginnt dort, wo die letzte aufgehört hat. Dauer zum Mitmachen: ca. 30 Minuten. Voraussetzung: [Teil 3](03-hausordnung.md).

## Video

[Video ansehen (MP4, 17 MB)](https://github.com/marcgarding54-create/AI-OS/releases/download/v1.0/teil-04-kurzzeitgedaechtnis.mp4)

Länge: 02:33

## Was du brauchst

- Obsidian mit Claudian (Teil 2) und deine Hausordnung (Teil 3). Weil sie es verlangt, legt Claude bei größeren Aufgaben erst einen Plan vor.
- Nichts zu installieren.

Drei Orte reichen:

| Ort | Wofür |
|---|---|
| **Brain Dump** (`01 Inbox/Brain Dump.md`) | alles Unsortierte |
| **Tagesnotiz** (`06 Tagesnotizen/JJJJ-MM-TT.md`) | eine Notiz je Tag |
| **Übertrag** (letzter Abschnitt der Tagesnotiz) | die einzige Liste für „was ist als Nächstes dran“ |

Dazu zwei Routinen, jeden Tag gleich:

| Du sagst | Claude tut |
|---|---|
| **„Guten Morgen“** | legt die Tagesnotiz für heute an, übernimmt den Übertrag der letzten Notiz (nichts doppelt), liest den Brain Dump und meldet Auffälliges, gibt einen Kurzbericht (Morgen zuerst, Entscheidungen, Wartendes) |
| **„Feierabend“** | sortiert den Brain Dump ein und fragt bei Unklarem nach, aktualisiert den Übertrag, streicht Erledigtes, leert den Brain Dump erst nach deinem Ok |

## Schritt für Schritt

1. **Claude:** Lass Claude beide Dateien und die zwei Routinen einrichten. Schreib den Prompt:

   ```text
   Richte mir eine Tagesroutine ein: Leg „01 Inbox/Brain Dump.md“ an und für heute eine Tagesnotiz in „06 Tagesnotizen“ (Dateiname JJJJ-MM-TT.md), die mit dem Abschnitt „## ⏭️ Übertrag“ endet, mit den Fächern Morgen zuerst, Ich muss entscheiden, Wartet auf andere, Bewusst nicht gemacht. Schreib die Start- und die End-Routine als Regeln in meine CLAUDE.md, sodass du sie ausführst, wenn ich „Guten Morgen“ oder „Feierabend“ sage.
   ```

   Die Überschrift „## ⏭️ Übertrag“ steht mit dem Pfeil-Symbol so im Prompt.

2. **Du:** Claude legt zuerst einen **Plan** vor (wegen der Hausordnung aus Teil 3). Fällt der Tag auf einen Freitag, fragt es, ob es dich beim Feierabend an den Wochenbericht erinnern soll. Gib den Plan frei, in eigenen Worten.

3. **Du:** Claude legt den Brain Dump und die erste Tagesnotiz an. Die Tagesnotiz endet mit dem Übertrag und seinen vier Fächern. Die beiden Routinen stehen jetzt in deiner `CLAUDE.md` (Abschnitt „Tagesroutine“).

4. **Du:** Tagsüber landet alles im Brain Dump, ungeordnet, so wie es kommt. Öffne `01 Inbox/Brain Dump.md` in Obsidian und schreibe Einfälle hinein, einen je Zeile. Du musst nicht überlegen, wohin sie gehören.

5. **Claude:** Am Abend:

   ```text
   Feierabend
   ```

   Claude sortiert jeden Eintrag ein: Erledigtes in den Tag, Offenes in die Fächer des Übertrags. Was unklar ist, fragt es nach. Antworte darauf. Den Brain Dump leert Claude erst, wenn du zustimmst.

6. **Claude:** Am nächsten Tag in einer **neuen Sitzung**:

   ```text
   Guten Morgen
   ```

   Claude legt die Notiz für heute an, übernimmt den Übertrag und sagt dir in wenigen Zeilen, was ansteht. Neue Einträge im Brain Dump meldet es als „Auffällig“ und fragt, was zu tun ist.

**Platzhalter:** Dateiname `JJJJ-MM-TT.md` steht für das Datum (zum Beispiel `2026-10-30.md`). Die Fächer und die Überschrift kannst du ändern, solange die Tagesnotiz mit dem Übertrag endet.

## Das siehst du im Video

| Zeit | Szene |
|---|---|
| 00:00 | Einstieg: Claude vergisst zwischen zwei Sitzungen, Titel „Teil 4: Das Kurzzeitgedächtnis“ |
| 00:15 | Prinzip: Brain Dump, Tagesnotiz, Übertrag am Ende |
| 00:30 | Zwei Routinen: „Guten Morgen“ und „Feierabend“ |
| 00:43 | Der Prompt, Claudes Plan mit der Freitags-Rückfrage |
| 00:59 | Der Auftrag noch einmal in Ruhe: erst die beiden Dateien, dann die zwei Routinen |
| 01:11 | Freigabe, `CLAUDE.md` mit Abschnitt „Tagesroutine“, Tagesnotiz mit vier Fächern |
| 01:25 | Tagsüber: Brain Dump mit fünf Einträgen |
| 01:33 | „Feierabend“: Einsortieren, Rückfragen, Brain Dump leer, Tagesnotiz mit gefülltem Übertrag |
| 01:54 | Montagmorgen: „Guten Morgen“ in neuer Sitzung, Kurzbericht mit „Auffällig im Brain Dump“ |
| 02:16 | Fertig, wenn …, Ausblick auf Teil 5 |

## Wenn es bei dir anders aussieht

- **Das Video zeigt Freitagabend und Montagmorgen.** Das war eine Einstellung bei der Aufnahme (die Uhr war auf diese Zeiten gestellt). Bei dir gilt das echte Datum. Du kannst „Feierabend“ und am nächsten Tag „Guten Morgen“ sagen.
- **Claude legt zuerst einen Plan vor und fragt nach**, weil deine Hausordnung es verlangt. Das ist gewollt.
- **Das Einsortieren passiert bei „Feierabend“, nicht morgens.** Morgens liest Claude den Brain Dump nur und meldet Auffälliges.
- **Der Brain Dump bleibt gefüllt**, bis du dem Leeren zustimmst.
- **Die Freitags-Erinnerung an den Wochenbericht** greift beim ersten „Feierabend“ am Freitag.
- **Der Übertrag wird zum Tagesbericht.** Halte ihn als Liste, Erledigtes fliegt raus.
- **Zwei Listen für Offenes** (Übertrag und eine Aufgaben-App): schaffe eine davon ab.
- **Claude führt die Routine nur halb aus.** Bitte Claude, jeden Schritt sichtbar abzuhaken.
- Die Routinen speichern erst ab Teil 5 per Git. Davor beendet „Feierabend“ ohne Hochladen.

## Fertig, wenn …

- [ ] Auf „Guten Morgen“ nennt Claude deinen Übertrag von gestern.
- [ ] Der Brain Dump ist nach dem Einsortieren leer.
- [ ] Es gibt genau einen Ort für „was ist als Nächstes dran“.

## Wenn du hängst

```text
Ich komme bei Teil 4 (Brain Dump, Tagesnotiz, Übertrag, Guten Morgen und Feierabend) nicht weiter. Das passiert: [beschreibe, was du siehst]. Prüf, ob die Dateien und die zwei Routinen in meiner CLAUDE.md richtig angelegt sind, und führ mich Schritt für Schritt durch einen Probelauf mit „Feierabend“.
```

[Weiter: Teil 5 Sichern](05-sichern.md)
