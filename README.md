# GRProt
# Analyse von Protokoll des Zürcher Stadtparlaments

Ausgewertet wurden die Protokolle von knapp 200 Sitzungen der Legislatur 2018-2022 des Zürcher Gemeinderats 

## 0 Checkliste

 - These formulieren:
 Anzahl und Umfanng der Wortmeldungen der einzlenen Mitglieder des Zürcher Stadtparlaments variieren sehr stark. Die Vielredner sind - gefühlt - fast ausschliesslich Männer. Frauen kommen deutlich weniger zu Wort. Auch die Parteien sind, was die Wortmeldungen betrifft, nicht unbedingt proportional zu ihrem Sitzanteil vertreten.
 
 - These checken: Relevanz? Neu? Aufwand/Ertrag?
 Es gab bereits vergleichbare Analysen von Redezeiten oder Anzahl Wortmeldungen in Parlamenten, unter anderem unter dem Aspekt der Beteiligung von Frauen. Neu ist - meines Wissens - dass schriftliche Protokolle als Datenquelle für eine Auswertung des Umfangs der Voten genutzt werden. 
 
 - Knackpunkt bestimmen.
 Die als PDF-Dateien veröffentlichten Protokolle sind nicht optimal strukturiert und enthalten zahlreiche Informationen, die aussortiert werden müssen. 
 
 - Briefing Person konsultieren
 entfällt
 
 - Daten beschaffen/reinigen/analysieren/visualisieren
 Die Beschaffung der öffentlich zugänglichen Protokolle war problemlos möglich, der Download konnte über ein API automatisiert werden. 
 Die Bereinigung und Aufbereitung der Daten war aufwändiger als zunächst erwartet.
 
 - Ergänzen durch klassische Recherche
Anfragen bei Parlamentsdiensten zum Start des offiziellen "Genderwatch-Protokolls" sowie bei der Urheberin des entsprechenden Vorstosses

 - Dokumentieren Code und statistische Annahmen
 Anmerkungen im Code
 
 - Link auf Publikation
bei Abgabe noch nicht publziert 

 - Aufwandlogbuch
 

## 1 Datenquelle

Als Datenquelle dienen öffentlich zugängliche schriftliche Protokolle der Gemeinderatssitzungen [(https://www.gemeinderat-zuerich.ch)](%28https://www.gemeinderat-zuerich.ch%29)

## 2 Auslesen der Voten

Die PDF-Dateien der Protokolle werden mit PDFMiner eingelesen. Das Extrahieren von Namen der RednerInnen und ihrer Voten erfolgt primär anhand der dafür verwendeten Fonts.
Mittels einer Korrekturfunktion werden falsch geschriebene Namen oder Parteizuordnungen korrigiert. Mittels API-Abfrage werden Details zu den Gemeinderatsmitgliedern abgerufen (unter anderem Geschlecht). 
Die Ergebnisse werden in einem pandas dataframe fortlaufend gespeichert. 

## 3 Auswertung

Das Dataframe umfasst über 9000 Einträge zu jedem einzelnen Votum von rund 180 GemeinderätInnen der Legislaturperiode 2018-2022. 
Wer sind die VielrednerInnen im Stadtparlament? Wie steht es um den Redeanteil der Frauen und innerhalb der Parteien?

## 4 Artikel

.

## 5 Aufwandlogbuch
 - November/Dezember 2022: erste Versuche zur automatisierten Auswertung der Protokolle. ca. 8 Stunden
 - Einlesen der Protokolle (PDF Files) mittels externem Tool [Parsr](https://github.com/axa-group/Parsr) ermöglichen: ca. 8 Stunden. Anschliessend werden die Daten aus den von Parsr aus den PDF-Protokollen erstellten JSON-files extrahiert. Aufwändig und fehleranfällig. ca. 8 Stunden
 - Methode finden, um die nur RednerInnen und ihre Voten herauszufiltern: 4 Stunden
 - Zahlreiche Fehler/Probleme in den Protokollen bereinigen (falsche geschriebene Namen, etc.) 8 Stunden
 - Januar/Februar 2023: Mit Unterstützung von ChatGPT zentrale Komponenten des Codes von Grund auf neu geschrieben. Die Daten werden jetzt mittels pdfminer direkt aus den PDFs extrahiert. Die Resultate sind deutlich besser als vorher. Eine neue Korrekturfunktion korrigiert falsch geschriebene Namen und Parteizuordnungen automatisch (bisher manuell). ca. 6 Stunden
 - Auswertungen und Grafiken: ca. 8 Stunden
 - Artikel schreiben: ca. 4 Stunden
 - Dokumentation, etc. ca. 4 Stunden
 
