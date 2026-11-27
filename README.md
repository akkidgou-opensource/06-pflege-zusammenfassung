# 06 · Pflege-Zusammenfassung

> Prototyp für den AKKI Hackathon 2026. Nur synthetische Daten, kein Medizinprodukt, kein Ersatz für die Übergabe am Bett.

**Bereich:** Station

**Idee:** Aus Vitalwerten, Labor, Medikation und Verlauf erstellt die KI eine strukturierte Stationszusammenfassung mit Hinweisen auf Risiken (z. B. Delir).

**Vorschlag zur Eingrenzung:** Ein Dummy-Fall, eine Übergabe-Zusammenfassung, ein Risiko (Delir).

## Warum
Übergaben und Visiten-Vorbereitung erfordern das Sichten vieler verstreuter Datenquellen. Risikopatientinnen und -patienten werden dabei leicht übersehen.

## Was am Ende stehen soll
- Import oder Eingabe von Vitalwerten, Labor, Medikation und Verlaufsnotizen (Dummy-Datensatz)
- Automatisch erzeugte Kurzzusammenfassung für Übergabe oder Visite
- Hervorhebung auffälliger Werte und Risikohinweise

**Erfolgskriterium:** Für mindestens einen Dummy-Fall liegt eine vollständige, korrekte Zusammenfassung vor.

## So startet ihr
1. Oben auf **Code → Download ZIP** klicken und entpacken.
2. Im entpackten Ordner ein Terminal öffnen und `claude` eingeben (bei Codex: `codex`).
3. `SPICKZETTEL.md` öffnen und mit Block 1 beginnen.
4. Zwischenstände hochladen: siehe `GITHUB_ANLEITUNG.md`.

## Was in diesem Repo liegt
| Datei | Wofür |
|---|---|
| `SPICKZETTEL.md` | Umsetzungsplan für 8 Stunden, Block für Block |
| `CLAUDE.md`, `AGENTS.md` | Dieselben Regeln für den Coding-Agenten (Claude Code liest die erste, Codex die zweite Datei) |
| `GITHUB_ANLEITUNG.md` | Eure Arbeit auf GitHub bringen, ohne Git-Kenntnisse |
| `daten/QUELLEN.md` | Offene und synthetische Datenquellen mit Lizenz |
| `daten/dummy_patient_01.json` | Ein frei erfundener Stationsfall (Vitalwerte, Labor, Medikation, Verlauf) |
| `daten/grascco/` | 62 synthetische deutsche Arztbriefe als Zusatzmaterial |
| `daten/synthea_auswahl/` | 10 vollständig künstliche Patientenakten als Tabellen (englisch) |

## Stolpersteine
- Nur mit synthetischen Daten arbeiten
- Umfang auf einen Beispielfall begrenzen
- Eine Zusammenfassung darf nichts erfinden: Jede Aussage muss sich auf einen Eintrag in den Daten zurückführen lassen

## Für Erfahrene
- Jede Aussage der Zusammenfassung mit dem Quelleintrag verlinken (Klick zeigt den Originalwert)
- Verlauf der Vitalwerte als Diagramm
- Zweiter Risikobereich, z. B. Sturz oder Dekubitus
