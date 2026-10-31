# Teil 8: Projekte planen

Ziel: Bevor gebaut wird, steht schriftlich fest, was gebaut wird und woran man merkt, dass es fertig ist. Dauer zum Mitmachen: ca. 30 Minuten je Vorhaben. Voraussetzung: [Teil 7](07-rezepte-und-rollen.md).

## Video

{{VIDEO_08}}

Länge: 02:21

## Was du brauchst

- Den Skill **grill-me**: Claude fragt dich eine Frage nach der anderen, bis der Plan steht. Quelle: [github.com/RobMitt/grill-me-skill](https://github.com/RobMitt/grill-me-skill). Skill-Grundlagen: [code.claude.com/docs/en/skills](https://code.claude.com/docs/en/skills)
- Eine Idee. Im Video: Der Wochenbericht soll freitags als Mail an das Team gehen.
- Ohne grill-me geht es auch: Lass in Schritt 3 den Satz „Nutze /grill-me und“ weg.

Erst ausfragen lassen, dann aufschreiben, dann bauen. Am Ende stehen zwei Dateien:

| Datei | Inhalt |
|---|---|
| `KICKOFF.md` | der Bauauftrag: Ziel, Umfang, Ausschlüsse, prüfbare Akzeptanzkriterien |
| `ENTSCHEIDUNGEN.md` | jede Entscheidung mit Datum und deinem Wortlaut. Was dort steht, schlägt Claude nicht neu vor. |

## Schritt für Schritt

1. **Du:** Installiere den Skill grill-me. Er ist eine Datei `SKILL.md` im Ordner `~/.claude/skills/grill-me/` (Windows: `%USERPROFILE%\.claude\skills\grill-me\`). Den Inhalt findest du im Repo [RobMitt/grill-me-skill](https://github.com/RobMitt/grill-me-skill). Oder lass Claude es tun:

   ```text
   Installiere mir den Skill grill-me von github.com/RobMitt/grill-me-skill. Zeig mir vorher den Inhalt der SKILL.md und erklär mir kurz, was er tut.
   ```

   Dieser Schritt ist im Video nicht zu sehen und wurde noch nicht gegen die Anleitung des Repos getestet (**ungeprüft**).

2. **Du:** Schreibe deine Idee in zwei Sätzen in den Brain Dump (`01 Inbox/Brain Dump.md`).

3. **Claude:** Gib den Auftrag:

   ```text
   Ich habe eine Idee: Der Wochenbericht soll freitags als Mail an mein Team gehen. Bisher kopiere ich ihn jedes Mal von Hand. Nutze /grill-me und frag mich eine Frage nach der anderen, bis alles geklärt ist. Schreib danach eine KICKOFF.md mit Ziel, Umfang, Ausschlüssen und prüfbaren Akzeptanzkriterien und eine ENTSCHEIDUNGEN.md mit Datum und meinem Wortlaut. Bau noch nichts.
   ```

   Der Auftrag hat vier Teile: (1) die Idee in zwei Sätzen, (2) „Nutze /grill-me, eine Frage nach der anderen“, (3) „KICKOFF.md und ENTSCHEIDUNGEN.md“, (4) „Bau noch nichts“. Der letzte Satz ist der wichtigste.

4. **Du:** Beantworte die Fragen. Claude stellt sie als Auswahlfelder, eine nach der anderen, einmal auch als Mehrfachauswahl. Es bezieht deine Hausordnung, dein Profil und die Regeln aus den früheren Teilen ein (zum Beispiel nie ohne Rückfrage senden, Adressen nur in die `.env`). Es fragt, was **nicht** dazugehört.

   Die Antworten im Video, als Beispiel (in der Reihenfolge der Fragen): Outlook / Microsoft 365 · Entwurf + manuelle Freigabe · Outlook-Verteiler / Gruppe · Mit Privat-Filter · Tag #privat am Stichpunkt · Kurzer Gruß + Text im Body · Sehr knapp · In der Freitags-Feierabend-Routine · Prüfung gegen Regeln · Vermerk in der Berichtsdatei · Ausschlüsse: Automatisches Senden, Bericht schreiben, Andere Wochentage/Empfänger · In .env · Probe-Entwurf an mich selbst · Abbruch + klare Meldung · Outlook-Signatur

5. **Du:** Claude fasst zusammen und nennt, was noch offen ist (im Video zum Beispiel, ob der Mail-Connector überhaupt Entwürfe anlegen kann). Danach schreibt es die beiden Dateien. Gebaut ist noch nichts, und genau so soll es sein.

6. **Du:** Lies die `KICKOFF.md`. Jedes Akzeptanzkriterium soll sagen, wie es bewiesen wird. Nicht: „Die Mail soll gut sein.“ Sondern: „Genau ein Entwurf liegt im Ordner, und nichts ist gesendet.“

**Platzhalter:** Der Satz mit der Idee ist das Video-Beispiel. Setze deine Idee in zwei Sätzen ein. Die Antworten in Schritt 4 sind Beispiele aus dem Video (dort wurde Outlook genutzt); antworte nach deiner Lage.

## Das siehst du im Video

| Zeit | Szene |
|---|---|
| 00:00 | Einstieg: Wer sofort bauen lässt, bekommt etwas, das niemand wollte, Titel „Teil 8: Projekte planen“ |
| 00:13 | Prinzip: ausfragen, aufschreiben, bauen; die zwei Dateien |
| 00:26 | Idee im Brain Dump, der Prompt, die erste Frage „Mail-Konto“ |
| 00:42 | Der Prompt noch einmal in Ruhe, in vier Teilen |
| 01:00 | Die Fragen: Auslöser, die Regel „nie ohne Rückfrage senden“, private Punkte |
| 01:15 | Ausschlüsse: kein automatisches Senden, Adresse des Verteilers in die `.env` |
| 01:27 | Nach fünfzehn Fragen: Zusammenfassung mit „Offen“ |
| 01:39 | `KICKOFF.md` mit elf Akzeptanzkriterien |
| 01:52 | `ENTSCHEIDUNGEN.md` mit Tabelle |
| 02:05 | Fertig, wenn …, Ausblick auf Teil 9 |

## Wenn es bei dir anders aussieht

- **Das Interview dauert zehn bis zwanzig Fragen.** Im Video waren es 15.
- **Die Fragen kommen als Auswahlfelder**, eine davon als Mehrfachauswahl, am Ende zwei auf einmal.
- **Claude zeigt in Fragen die angebundene Mailadresse.** Das kann eine private sein. Denk daran, wenn du Bildschirmfotos teilst.
- **Deine `KICKOFF.md` hat andere Kriterien.** Im Video gibt es elf Akzeptanzkriterien. Teil 9 greift auf die Kriterien 4 bis 6 zu; bei dir stehen die passenden Kriterien vielleicht anders.
- **Ohne grill-me** funktioniert der Prompt auch, dann ohne `/grill-me`.
- **grill-me:** Das Repo gibt keine Lizenz an (GitHub-Angabe „keine“). Ob die Weitergabe frei ist, ist **ungeprüft**. Der Windows-Pfad `%USERPROFILE%\.claude\skills\` ist aus dem Mac-Pfad abgeleitet und von der Anleitung des Repos nicht bestätigt (**ungeprüft**).
- **Zu früh bauen.** Der Umbau kostet mehr als die Planung. Kriterien wie „schön“ oder „schnell“ ohne Zahl oder Beleg lassen sich nicht prüfen.
- **Beschlüsse stehen nur im Chat.** Nach der Sitzung sind sie weg; deshalb gehören sie in die `ENTSCHEIDUNGEN.md`.

## Fertig, wenn …

- [ ] Jedes Akzeptanzkriterium nennt seinen Nachweis.
- [ ] Du kannst in drei Sätzen sagen, was nicht gebaut wird.
- [ ] Die Beschlüsse stehen mit Datum in der `ENTSCHEIDUNGEN.md`.

## Wenn du hängst

```text
Ich komme bei Teil 8 (Projekt planen mit grill-me, KICKOFF.md und ENTSCHEIDUNGEN.md) nicht weiter. Das passiert: [beschreibe, was du siehst]. Prüf, ob der Skill grill-me installiert ist, und frag mich zu meiner Idee [deine Idee in zwei Sätzen] eine Frage nach der anderen. Bau noch nichts.
```

[Weiter: Teil 9 Prüfen statt glauben](09-pruefen-statt-glauben.md)
