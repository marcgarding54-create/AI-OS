# Teil 2: Der Arbeitsplatz

Ziel: Deine Notizen liegen in einem Obsidian-Ordner, und du sprichst mit Claude direkt neben ihnen. Dauer zum Mitmachen: ca. 45 Minuten. Voraussetzung: [Teil 1](01-claude-code-installieren.md).

## Video

{{VIDEO_02}}

Länge: 02:50

## Was du brauchst

- **Obsidian**, eine Notiz-App. Deine Notizen sind normale Textdateien in einem Ordner, genau diese Dateien liest und schreibt Claude. Kostenlos, auch für die Arbeit. [obsidian.md/download](https://obsidian.md/download)
- **Claudian**, ein Obsidian-Plugin: der Chat mit Claude Code direkt in Obsidian. Kostenlos. Voraussetzung: Claude Code ist installiert (Teil 1), Obsidian 1.13.0 oder neuer, nur am Computer (nicht auf dem Handy). [Claudian im Obsidian-Katalog](https://community.obsidian.md/plugins/realclaudian), Quellcode: [github.com/YishenTu/claudian](https://github.com/YishenTu/claudian)
- Dein Ordner `wochenbericht` aus Teil 1.

## Schritt für Schritt

1. **Du:** Lade Obsidian von [obsidian.md/download](https://obsidian.md/download) herunter und installiere es wie jedes andere Programm. Mac: „Mac Universal“ (.dmg). Windows: der Windows-Installer. Danach sieht alles auf beiden Systemen gleich aus.

2. **Du:** Starte Obsidian. Wähle im Startfenster **Ordner als Vault öffnen** und nimm den Ordner `wochenbericht` aus Teil 1. Obsidian nennt einen solchen Ordner **Vault**. Du siehst die Datei `woche-43`, die Claude in Teil 1 angelegt hat, jetzt als ordentliche Notiz. (Ohne Teil 1 geht auch **Einen neuen Vault erstellen**.)

3. **Du:** Erlaube Erweiterungen. Öffne die Einstellungen über das Zahnrad unten links. Gehe auf **Externe Erweiterungen** und klicke auf **Eingeschränkten Modus verlassen**. Dann auf **Durchsuchen**.

4. **Du:** Installiere Claudian. Suche nach **Claudian**. Es gibt viele Erweiterungen mit ähnlichem Namen (zum Beispiel Claudian Plus, Oh My Claudian). Nimm die von **Yishen Tu** mit der ID `realclaudian`, sie hat mit Abstand die meisten Downloads. Klicke auf **Installieren** und danach auf **Aktivieren**.

5. **Du:** Schalte ein Modell frei. Claudian startet ohne Modell. Öffne die Einstellungen, klicke links auf **Claudian**, dann oben auf **Providers**. Setze unter **Models** einen Haken, zum Beispiel bei **Sonnet**. Wähle das Modell danach unten im Chat aus.

6. **Claude:** Öffne Claudian über das neue Symbol in der linken Leiste und schreibe deine erste Nachricht:

   ```text
   Fass mir woche-43 in einem Satz zusammen.
   ```

   Claude liest die Notiz und antwortet direkt daneben. Unter Windows: starte Obsidian vorher einmal neu, damit Claudian Claude findet.

7. **Claude:** Lass Claude den Vault einrichten. Schreibe den Prompt in Claudian:

   ```text
   Leg in diesem Vault die Ordner „00 Kontext“, „01 Inbox“, „02 Projekte“, „06 Tagesnotizen“ und „07 Archiv“ an. Dann interviewe mich mit fünf Fragen (Beruf, typische Aufgaben, Werkzeuge, Ziele, wie ich Texte mag) und schreib daraus die Datei „00 Kontext/Über mich.md“.
   ```

   Claude legt die fünf Ordner an und stellt dir die Fragen als Auswahlfelder. Du klickst die Antworten an und bestätigst mit **Submit answers**. Daraus schreibt Claude die Datei „Über mich“.

8. **Du:** Lies „00 Kontext/Über mich.md“. Sie soll dich so beschreiben, dass du zustimmst. Sonst sag Claude, was zu ändern ist.

**Platzhalter:** `woche-43` ist die Datei aus Teil 1. Hast du sie anders genannt, nimm deinen Namen. Die Ordnernamen im Prompt (mit den Nummern) sind genau so gemeint; die Nummern halten die Reihenfolge fest.

## Das siehst du im Video

| Zeit | Szene |
|---|---|
| 00:00 | Einstieg: Das Terminal ist kein Ort zum Arbeiten, Titel „Teil 2: Der Arbeitsplatz“ |
| 00:16 | Prinzip: Notizen sind Textdateien in einem Ordner, Obsidian und Claude lesen dieselben Dateien |
| 00:33 | Obsidian herunterladen und installieren |
| 00:46 | Ordner als Vault öffnen, `woche-43` erscheint als Notiz |
| 01:01 | Einstellungen › Externe Erweiterungen › Eingeschränkten Modus verlassen › Durchsuchen |
| 01:16 | „Claudian“ suchen, die von Yishen Tu wählen, Installieren, Aktivieren |
| 01:30 | Modell freischalten: Claudian › Providers › Models, Haken bei Sonnet |
| 01:48 | Erste Nachricht in Claudian |
| 02:02 | Der Prompt zum Einrichten des Vaults, Interview, Datei „Über mich“ |
| 02:21 | Der Auftrag noch einmal in Ruhe: erst die Ordner, dann das Interview, dann die Datei |
| 02:32 | Fertig, wenn …, Ausblick auf Teil 3 |

## Wenn es bei dir anders aussieht

- **„Model unavailable“ im Chat, oder die Warnung „No Claude Code models are enabled“.** Claudian hat noch kein Modell freigeschaltet. Einstellungen › Claudian › Providers › Models: Haken setzen, danach im Chat auswählen (Schritt 5).
- **Deutsche Begriffe.** In Obsidian 1.14 mit deutscher Oberfläche heißt der Bereich **Externe Erweiterungen** und der Knopf **Eingeschränkten Modus verlassen**. Einstellungen und Plugin-Katalog öffnen als eigene Fenster. Die offizielle Anleitung nennt den Schritt „Community-Plugins aktivieren“. Bei englischer Oberfläche heißen die Menüs vermutlich „Community plugins“ und „Turn on community plugins“ (**ungeprüft**).
- **Viele Nachbauten.** Der Katalog enthält Erweiterungen mit ähnlichem Namen. Prüfe Autor (**Yishen Tu**) und ID (`realclaudian`).
- **Der Katalog prüft Plugins nicht von Hand.** Er prüft nach jeder Aktualisierung automatisch, im Katalog steht „not manually reviewed“. Erweiterungen führen fremden Code aus. Hinweise von Obsidian: [obsidian.md/help/community-plugins](https://obsidian.md/help/community-plugins)
- **Claudian findet Claude nicht.** Claude Code muss installiert sein (Teil 1). Danach Obsidian neu starten. Unter Windows nutzt Claudian die PATH-Variable des Benutzers.
- **Claudian verschiebt keine Dateien.** Es verschiebt nur über die Obsidian-CLI. Ohne sie lässt Claude die Datei liegen und sagt das. Deshalb verschiebt der Prompt in diesem Teil nichts.
- **Das Interview erscheint als Auswahlfelder**, nicht als Fließtext. Klicke an und bestätige mit „Submit answers“.
- **Dein Ordner heißt anders** oder du hast Teil 1 nicht gemacht: Nimm den Ordner, den du nutzen willst.

## Fertig, wenn …

- [ ] Claude antwortet dir in Obsidian im Claudian-Fenster.
- [ ] Die fünf Ordner sind im Vault sichtbar.
- [ ] „00 Kontext/Über mich.md“ beschreibt dich so, dass du zustimmst.

## Wenn du hängst

Öffne Claudian (oder starte `claude` im Terminal) und schreib:

```text
Ich komme bei Teil 2 (Obsidian und Claudian einrichten) nicht weiter. Das passiert: [beschreibe, was du siehst oder welche Meldung kommt]. Ich habe [Mac oder Windows]. Erklär mir in einfachen Worten, woran es liegt, und führ mich Schritt für Schritt zur Lösung.
```

[Weiter: Teil 3 Die Hausordnung](03-hausordnung.md)
