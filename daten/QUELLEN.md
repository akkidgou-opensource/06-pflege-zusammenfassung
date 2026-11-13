# Datenquellen Pflege-Zusammenfassung

## Im Repo
| Datei | Inhalt | Herkunft und Lizenz |
|---|---|---|
| `dummy_patient_01.json` | Ein vollständiger Stationsfall: Stammdaten, Vitalwerte, Labor, Medikation, Zugänge, Bilanz, Verlaufsnotizen | Frei erfunden für den Hackathon, medizinisch nicht geprüft. Frei verwendbar. |
| `grascco/` | 62 synthetische deutsche Arztbriefe | [GraSCCo, Zenodo 10.5281/zenodo.6539131](https://doi.org/10.5281/zenodo.6539131), CC BY 4.0 |
| `synthea_auswahl/` | 10 vollständig künstliche Patientenakten als CSV-Tabellen: Stammdaten, Aufenthalte, Diagnosen, Medikation, Messwerte und Labor, Eingriffe, Pflegepläne. Ausgewählt wurden die 10 Personen mit den meisten stationären Aufenthalten. | Offizielle Beispieldaten von [Synthea](https://github.com/synthetichealth/synthea) (Werkzeug unter Apache-2.0). Spalten mit Ausweisnummern und Adressen wurden entfernt. |

## Weitere offene Quellen (nur verlinkt)
| Quelle | Inhalt | Lizenz laut Anbieter | Hinweis |
|---|---|---|---|
| [Synthea](https://github.com/synthetichealth/synthea) | Werkzeug, das beliebig viele vollständig künstliche Patientenakten erzeugt | Apache-2.0 | Eine Auswahl liegt schon im Repo. US-amerikanisch geprägt, englisch, Verläufe über viele Jahre statt einzelner Stationstage. |
| [MIMIC-IV Clinical Database Demo](https://physionet.org/content/mimic-iv-demo/) | 100 Intensiv- und Klinikfälle mit Labor, Medikation und Vitalwerten, ohne Freitext | Open Database License | **Echte, anonymisierte Patientendaten** aus Boston. Offen zugänglich, widerspricht aber der Hackathon-Regel „nur synthetische Daten“. Nur nach Rücksprache mit den Mentor:innen. |

## Empfehlung für den Hackathon
- Mit `dummy_patient_01.json` beginnen. Der Fall enthält absichtlich mehrere Hinweise auf ein Delir-Risiko, die über verschiedene Bereiche verstreut sind.
- Einen zweiten Fall als Kopie anlegen und die Werte ändern. So entsteht ein Blind-Fall im selben Format.
- GraSCCo-Briefe eignen sich als Vorgeschichte, sind aber medizinisch nicht immer plausibel.

## Bei Verwendung angeben
Modersohn L, Schulz S, Lohr C, Hahn U. GRASCCO – The First Publicly Shareable, Multiply-Alienated German Clinical Text Corpus. Stud Health Technol Inform. 2022;296:66-72.
