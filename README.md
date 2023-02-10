# GRProt

Analyse von knapp 200 Protokollen des Zürcher Stadtparlaments der Legislatur 2018-2022. 

## 0 Checkliste

 - These formulieren:
 Anzahl und Umfanng der Wortmeldungen der einzlenen Mitglieder des Zürcher Stadtparlaments variieren stark. Die Vielredner sind - gefühlt - fast ausschliesslich männlich. Frauen kommen deutlich weniger zu Wort. 
 - These checken: Relevanz? Neu? Aufwand/Ertrag?
 Es gab bereits vergleichbare Analysen von Redezeiten oder Anzahl Wortmeldungen in Parlamenten, unter anderem unter dem Aspekt der Beteiligung von Frauen. Neu ist - meines Wissens - die schriftlichen Protokolle und die Länge der einzelnen Voten als Datenquelle nutzen. 
 - Knackpunkt bestimmen.
 Die als PDF-Dateien veröffentlichten Protokolle sind nicht optimal strukturiert und enthalten zahlreiche Informationen, die aussortiert werden müssen. 
 - Briefing Person konsultieren
 - Daten beschaffen/reinigen/analysieren/visualisieren
 Die Beschaffung der öffentlich zugänglichen Protokolle war problemlos möglich, der Download konnte über ein API automatisiert werden. 
 Die Bereinigung und Aufbereitung der Daten war aufwändiger als zunächst erwartet.
 - Ergänzen durch klassische Recherche
 - Dokumentieren Code und statistische Annahmen
 - Link auf Publikation
 - Aufwandlogbuch
 - 

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

You can delete the current file by clicking the **Remove** button in the file explorer. The file will be moved into the **Trash** folder and automatically deleted after 7 days of inactivity.

## 5 Aufwandlogbuch

 - Einlesen der Protokolle (PDF Files) ermöglichen: 4 Stunden
 - Methode finden, um die nur RednerInnen und ihre Voten herauszufiltern: 4 Stunden
 - Zahlreiche Fehler/Probleme in den Protokollen bereinigen (falsche geschriebene Namen, etc.) 8 Stunden
 - Auswertung 4 Stunden
