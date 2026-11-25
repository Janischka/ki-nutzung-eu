# KI-Boom – wächst Europas digitale Kluft?

Eine datenjournalistische Analyse mit Python.

Immer mehr Unternehmen setzen auf künstliche Intelligenz. Doch wie unterschiedlich entwickelt sich die KI-Nutzung in den EU-Ländern? Holen bisherige Nachzügler auf oder wächst der Abstand zwischen Vorreitern und Schlusslichtern?

## Die wichtigsten Ergebnisse

- Der Anteil der Unternehmen, die KI einsetzen, ist EU-weit von 7,7 Prozent im Jahr 2021 auf knapp 20 Prozent im Jahr 2025 gestiegen.
- Der Abstand zwischen dem Spitzenreiter und dem Schlusslicht ist gewachsen: von 22,5 auf 36,8 Prozentpunkte.
- Gemessen am insgesamt gestiegenen Nutzungsniveau sind die Unterschiede zwischen den Ländern hingegen kleiner geworden.
- Estland macht im Ranking der 24 zeitlich verglichenen EU-Länder den größten Sprung.

## Wo Unternehmen besonders häufig KI nutzen

Dänemark führt das EU-Ranking 2025 an: Rund 42 Prozent der Unternehmen setzen dort KI ein. Es folgen Finnland (37,8 Prozent) und Schweden (35 Prozent). In Deutschland ist es rund jedes vierte Unternehmen (26 Prozent), in Rumänien lediglich jedes zwanzigste (5,2 Prozent).

## Wächst die digitale Kluft?

Um diese Frage zu beantworten, wurden verschiedene statistische Streuungsmaße berechnet.

| Streuungsmaß                         |  2021 |  2023 |  2024 |  2025 |
| ------------------------------------ | ----: | ----: | ----: | ----: |
| Spannweite (Prozentpunkte)           | 22,51 | 13,66 | 24,51 | 36,82 |
| Standardabweichung (Prozentpunkte)   |  4,94 |  4,09 |  7,04 | 10,07 |
| Interquartilsabstand (Prozentpunkte) |  6,74 |  6,70 | 11,89 | 16,09 |
| Variationskoeffizient (%)            | 64,09 | 49,71 | 49,32 | 48,56 |

Die Ergebnisse zeigen zwei unterschiedliche Entwicklungen:

- Die absoluten Unterschiede zwischen den Ländern sind größer geworden – nicht nur zwischen Spitzenreiter und Schlusslicht, sondern auch im Mittelfeld.
- Setzt man die Unterschiede ins Verhältnis zur durchschnittlichen KI-Nutzung der Länder, sind sie seit 2021 hingegen kleiner geworden.

Die Frage nach einer wachsenden digitalen Kluft lässt sich also nicht pauschal mit Ja oder Nein beantworten.

## Welche Länder aufholen

In allen 24 Ländern, die für den individuellen Zeitvergleich berücksichtigt wurden, ist die KI-Nutzung zwischen 2021 und 2025 gestiegen.

Besonders auffällig ist Estland: Dort stieg der Anteil der Unternehmen, die KI nutzen, von 2,8 auf 23,4 Prozent. Im Ländervergleich kletterte Estland von Platz 21 auf Platz 7.

Auch Rumänien verzeichnet einen hohen relativen Zuwachs. Dennoch bleibt das Land Schlusslicht. Das zeigt, warum es wichtig ist, bei Wachstumsraten auch das Ausgangsniveau zu berücksichtigen.

## Datengrundlage

Die Analyse basiert auf dem Eurostat-Datensatz *Artificial intelligence by size class of enterprise* (`isoc_eb_ai`).

- Untersuchungsgebiet: 27 EU-Mitgliedstaaten
- Erhebungsjahre: 2021, 2023, 2024 und 2025
- Untersuchungseinheit: Unternehmen mit mindestens zehn Beschäftigten in den erfassten Wirtschaftszweigen
- Indikator: Anteil der Unternehmen, die mindestens eine der abgefragten KI-Technologien nutzen
- Datenformat: SDMX-CSV
- Datenabruf: November 2026

**Quellen:**

- [Eurostat – Originaldatensatz](https://ec.europa.eu/eurostat/databrowser/view/isoc_eb_ai/default/table?lang=de)
- [Eurostat – Erhebungsmethodik und Metadaten](https://ec.europa.eu/eurostat/cache/metadata/en/isoc_e_esms.htm)
- [Eurostat – Use of artificial intelligence in enterprises](https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Use_of_artificial_intelligence_in_enterprises)

## Methodisches Vorgehen

- Aufbereitung und Filterung der Rohdaten
- Prüfung auf fehlende Werte, Dubletten und Qualitätskennzeichnungen
- Berechnung verschiedener Streuungsmaße
- Berechnung absoluter und relativer Zuwächse sowie Rangveränderungen
- Visualisierung der Ergebnisse

## Einschränkungen der Daten

- **Zeitreihenbrüche:** Frankreich und Schweden (2023) sowie die Niederlande (2025) weisen laut Eurostat Zeitreihenbrüche auf. Für die individuellen Entwicklungsvergleiche wurden diese Länder ausgeschlossen. Eine prüfende Analyse der Streuungsmaße ohne diese drei Länder bestätigt die zentralen Erkenntnis.
- **Vergleichbarkeit:** Veränderungen der abgefragten KI-Technologien können die zeitliche Vergleichbarkeit zusätzlich einschränken.
- **Datenlücke:** Für 2022 liegen keine Werte vor.
- **Erhebungsumfang:** Unternehmen mit weniger als zehn Beschäftigten und bestimmte Wirtschaftszweige werden nicht erfasst.
- **Aussagekraft:** Die Daten zeigen, wie verbreitet die KI-Nutzung ist – nicht, wie intensiv oder erfolgreich Unternehmen KI einsetzen. Auch die Ursachen für die Länderunterschiede lassen sich daraus nicht ableiten.

## Über das Projekt

Dieses Projekt ist Teil meiner praktischen Weiterbildung im Datenjournalismus. Ziel war es, meine Kenntnisse in der programmatischen Datenaufbereitung, deskriptiven Statistik, Datenvisualisierung und reproduzierbaren Datenanalyse auszubauen.

Bei der Entwicklung des Analysekonzepts, der Programmierung und der statistischen Interpretation habe ich ChatGPT als Lern- und Arbeitsassistenz genutzt.

## Technische Umsetzung

Python · Pandas · Matplotlib · JupyterLab · Docker

Die einzelnen Analyseschritte sind im Jupyter-Notebook `analyse.ipynb` dokumentiert. Die Rohdaten und exportierten Grafiken sind im Repository enthalten.

## Analyse reproduzieren

Voraussetzung: Docker.

Im Projektverzeichnis ausführen:

```bash
docker build -t ki-europa .
docker run --rm -p 127.0.0.1:8888:8888 ki-europa
```

Den im Terminal ausgegebenen lokalen Link im Browser öffnen, das Notebook `analyse.ipynb` auswählen und über **Kernel → Restart Kernel and Run All Cells** ausführen.

Eine separate Installation von Python oder weiteren Bibliotheken ist nicht erforderlich.
