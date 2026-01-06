# German-Rent-Analysis
Dieses Projekt analysiert einen Datensatz von über **268.000 Immobilieninseraten** in Deutschland, um die zentralen Preistreiber auf dem Mietmarkt zu identifizieren. Der Fokus liegt auf der geografischen Verteilung, dem Einfluss des Baujahres und der Ausstattung (z. B. Einbauküchen).
# Mietpreis-Analyse Deutschland (SQL & Tableau)

## Projektübersicht
Dieses Projekt analysiert einen Datensatz von über **268.000 Immobilieninseraten** in Deutschland, um die zentralen Preistreiber auf dem Mietmarkt zu identifizieren. Der Fokus liegt auf der geografischen Verteilung, dem Einfluss des Baujahres und der Ausstattung (z. B. Einbauküchen).

## Tech Stack
* **Datenquelle:** Kaggle / ImmoScout24 (Rohdaten: ~268k Zeilen)
* **Datenbanksystem:** Google BigQuery (SQL)
* **Visualisierung:** Tableau Desktop
* **Speicherung:** Google Cloud Storage

## Analyse-Prozess

### 1. Data Cleaning & Transformation (SQL)
Die Rohdaten wurden in BigQuery bereinigt, um die Validität der Analyse sicherzustellen:
* **Handling Missing Values:** Entfernung von Inseraten ohne Mietpreis- oder Flächenangaben.
* **Ausreißer-Bereinigung:** Ausschluss von unrealistischen Werten (z. B. 0 € Miete oder Tippfehler bei der Wohnfläche).
* **Feature Engineering:** Berechnung des Preises pro Quadratmeter (`price_per_sqm`) und Kategorisierung von Baujahren in Epochen (Altbau, Nachkriegsbau, Neubau).

### 2. Explorative Datenanalyse (EDA)
Mithilfe von SQL wurden folgende Kernfragen beantwortet:
* **Regionales Benchmarking:** Vergleich der Durchschnittsmieten pro Bundesland zum nationalen Durchschnitt mittels Window Functions (`AVG() OVER()`).
* **Korrelationsanalyse:** Untersuchung des Einflusses von Einbauküchen auf den Quadratmeterpreis.

### 3. Visualisierung (Tableau)
Ein interaktives Dashboard wurde erstellt, um die Ergebnisse zugänglich zu machen:
* **Choropleth Map:** Darstellung der Mietpreisdichte nach Bundesländern.
* **Trend-Analyse:** Balkendiagramme zur Darstellung der Mietpreisentwicklung nach Baujahres-Epochen.
* **Interaktive Filter:** Nutzer können die Karte filtern, um spezifische regionale Statistiken zu erhalten.

## Key Insights
* **Nord-Süd-Gefälle:** Metropolen wie Hamburg und München liegen signifikant über dem nationalen Benchmark.
* **Neubau-Premium:** Wohnungen ab Baujahr 2016 erzielen im Schnitt eine um X% höhere Miete als der Bestand.
* **Ausstattungs-Faktor:** Das Vorhandensein einer Einbauküche ist einer der stärksten Treiber für den Quadratmeterpreis.

## Projekt-Dateien
* `/sql_queries`: Enthält alle SQL-Skripte für Cleaning und Analyse.
* `/data_exports`: CSV-Dateien der aggregierten Ergebnisse für Tableau.
* `Mietpreis_Dashboard_Link`: [https://public.tableau.com/views/Dashboard_Miete_Deutschland/Dashboard1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link]

---
*Erstellt als Teil meines Data Analyst Portfolios.*
