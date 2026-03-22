---
layout: page
title: CSV-Format
permalink: /csv-format/
---

## CSV Import & Export

FinCheck unterstützt den Import und Export von Transaktionen im CSV-Format. So kannst du deine Finanzdaten sichern oder aus anderen Apps übernehmen.

### Format

Die CSV-Datei muss **UTF-8-kodiert** sein und folgende Spalten in genau dieser Reihenfolge enthalten:

| Spalte | Beschreibung | Pflicht | Beispiel |
|--------|-------------|---------|----------|
| Date | Datum und Uhrzeit | Ja | `2026-01-15 09:00` |
| Category | Name der Kategorie | Nein | `Lebensmittel` |
| Amount | Betrag (positiv = Einnahme, negativ = Ausgabe) | Ja | `-45.80` |
| Recurrence | Wiederkehrend (1 = monatlich, 0 = einmalig) | Ja | `0` |
| Description | Beschreibung | Ja | `Wocheneinkauf` |

### Regeln

- Die **erste Zeile** muss exakt die Kopfzeile sein: `"Date","Category","Amount","Recurrence","Description"`
- Alle Felder werden in **Anführungszeichen** eingeschlossen
- **Trennzeichen** ist das Komma (`,`)
- **Datumsformat:** `yyyy-MM-dd HH:mm` (z.B. `2026-01-15 09:00`)
- **Beträge** verwenden einen Punkt als Dezimaltrennzeichen (z.B. `-45.80`)
- Wenn eine **Kategorie** beim Import nicht in der App existiert, wird die Transaktion ohne Kategorie importiert
- **Leere Zeilen** werden übersprungen

### Beispiel

```csv
"Date","Category","Amount","Recurrence","Description"
"2026-01-15 09:00","Gehalt","2800.00","1","Monatliches Gehalt"
"2026-01-16 12:30","Lebensmittel","-45.80","0","Wocheneinkauf"
"2026-01-17 08:00","Miete","-950.00","1","Kaltmiete"
"2026-01-18 14:15","","-12.50","0","Geschenk für Lisa"
```

### Vorlage herunterladen

[**fincheck_vorlage.csv**]({{ site.baseurl }}/assets/downloads/fincheck_vorlage.csv) — Beispieldatei mit 4 Transaktionen, die du direkt in FinCheck importieren kannst.

---

Bei Fragen erreichst du mich unter [elmar.bickel@posteo.de](mailto:elmar.bickel@posteo.de).
