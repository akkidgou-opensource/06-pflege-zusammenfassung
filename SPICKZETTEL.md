# Spickzettel Pflege-Zusammenfassung · 8 Stunden

Acht Blöcke. Jeden Prompt in Claude Code kopieren, das Ergebnis prüfen, dann weiter. Wer schneller ist, baut frei, die „Fertig, wenn“-Punkte gelten trotzdem.

| Block | Zeit | Thema |
|---|---|---|
| 1 | 30 Min. | Setup |
| 2 | 45 Min. | Vorgaben: Aufbau der Übergabe, Risikozeichen |
| 3 | 60 Min. | Daten laden und anzeigen |
| 4 | 60 Min. | KI-Zusammenfassung |
| 5 | 75 Min. | Auffällige Werte und Risikohinweise |
| 6 | 75 Min. | Auf Richtigkeit prüfen |
| 7 | 45 Min. | Robustheit |
| 8 | 60 Min. | Ergebnis, Demo, Pitch |

Bleiben 30 Minuten Puffer.

## Block 1 · Setup
Schlüssel eintragen: `.env.example` zu `.env` kopieren und den ausgehändigten Schlüssel eintragen (im Texteditor, nicht über Claude Code).
```
Lies README.md und CLAUDE.md und sieh dir daten/dummy_patient_01.json an. Prüfe, ob Node.js ab Version 20 installiert ist, und lege die leeren Ordner prompt und ergebnisse an. Beschreibe mir in fünf Sätzen, welche Daten der Dummy-Fall enthält.
```
**Fertig, wenn:** Node passt, `.env` existiert, alle kennen den Dummy-Fall.

## Block 2 · Vorgaben (ohne Code)
In `spec.md` festlegen:
- Aufbau der Übergabe (z. B. nach einem Schema, das ihr von eurer Station kennt)
- Welche Werte gelten als auffällig? Grenzen mit Quelle oder als „offen“ markiert
- Welche Zeichen sprechen für ein Delir-Risiko? Mit Quelle
- Was die App nie tut: Diagnosen stellen, Medikamente an- oder absetzen

**Fertig, wenn:** `spec.md` von zwei Personen gegengelesen ist, idealerweise eine davon aus der Pflege.

## Block 3 · Daten laden und anzeigen
```
Baue die Grundversion: server.js und public/index.html. Die Seite lädt daten/dummy_patient_01.json und zeigt vier Bereiche: Stammdaten, Vitalwerte als Tabelle nach Zeit, Labor als Tabelle, Medikation und Verlaufsnotizen. Zusätzlich lässt sich eine andere JSON-Datei im selben Format hochladen. Der Hinweis aus CLAUDE.md ist immer sichtbar.
```
**Fertig, wenn:** der Dummy-Fall auf Laptop und Handy lesbar angezeigt wird.

## Block 4 · KI-Zusammenfassung
```
Ergänze den Button „Übergabe erstellen“. Er schickt die Falldaten an einen Endpunkt /api/zusammenfassung, der die Anthropic Messages API aufruft. Der System-Prompt wird bei jeder Anfrage frisch aus prompt/system.md gelesen und enthält den Übergabe-Aufbau WORTGETREU aus spec.md. Die KI verwendet ausschließlich Angaben aus den Falldaten und schreibt „nicht dokumentiert“, wenn etwas fehlt. Schlüssel und Modell kommen nur aus .env.
```
**Fertig, wenn:** eine Zusammenfassung im festgelegten Aufbau erscheint.

## Block 5 · Auffällige Werte und Risikohinweise
```
Stelle die Ausgabe auf JSON um mit den Feldern: zusammenfassung (nach Abschnitten), auffaellige_werte (Wert, Zeitpunkt, Grund), risikohinweise (Risiko, Begründung, Belege aus den Daten), offene_punkte. Übernimm Grenzwerte und Risikozeichen WORTGETREU aus spec.md. Zeige Risikohinweise oben in einem farbigen Kasten, jeder Hinweis nennt die Einträge, auf denen er beruht.
```
**Fertig, wenn:** jeder Risikohinweis mindestens einen Beleg aus den Daten nennt.

## Block 6 · Auf Richtigkeit prüfen
Zeile für Zeile gegen die Daten prüfen:
- Stimmt jede Zahl? Stimmt jeder Zeitpunkt?
- Wurde etwas Wichtiges weggelassen?
- Steht etwas in der Zusammenfassung, das nicht in den Daten steht?

Funde in einer Tabelle notieren, pro Durchlauf **eine** Prompt-Änderung. Danach einen zweiten Dummy-Fall selbst anlegen (Kopie der JSON-Datei, Werte ändern) und als Blind-Fall verwenden.

**Fertig, wenn:** drei dokumentierte Durchläufe vorliegen.

## Block 7 · Robustheit
```
Mache die App robuster, ohne prompt/system.md zu ändern: verständliche Meldung bei ungültiger oder unvollständiger JSON-Datei, bei fehlendem Netz und bei Zeitüberschreitung, jeweils mit „Erneut versuchen“. Ladeanzeige mit Sekunden. Fehlen ganze Bereiche (z. B. kein Labor), steht das sichtbar in der Übergabe.
```
**Fertig, wenn:** eine absichtlich unvollständige Datei sauber behandelt wird.

## Block 8 · Ergebnis, Demo, Pitch
- Blind-Fall **einmal** laufen lassen, Ergebnis nicht nachbessern
- `ergebnis.md`: Aufbau, gefundene Fehler, Limitationen (ein bis zwei erfundene Fälle, keine echten Kurven)
- Demo zweimal durchspielen, Screenshots als Backup
- Pitch: Problem, Live-Demo, wie geprüft, nächste Schritte
