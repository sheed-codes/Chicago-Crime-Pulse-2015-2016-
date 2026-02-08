# Chicago-Crime-Pulse-2015-2016-
Use SQL + Python to identify (1) which offense categories drive volume, (2) how arrest rates differ by crime type, and (3) where/when spikes show up over time.

# Chicago Crime Pulse (2015–2016): SQL + Python Analysis

This project analyzes Chicago crime incident data for 2015–2016 using a hybrid workflow:
- **SQL (SQLite)** for fast aggregation and metrics
- **Python (pandas + matplotlib)** for visualization and trend analysis

## Questions I asked
1. Which **primary offense types** drive the most incidents?
2. How does **arrest rate** vary by offense type and year?
3. Are there **monthly spikes (anomalies)** that stand out compared to a baseline?

## Dataset
Data is ingested from a public API endpoint into a local SQLite database table called `crime`.
The current dataset coverage is **2015–2016** (pipeline is designed to extend to additional years).

## Methods (Analyst Workflow)
- Loaded data into SQLite and verified schema + date coverage.
- Wrote SQL queries to produce:
  - Incidents by `primary_type` and `year`
  - Arrest rate trends by `primary_type` and `year`
  - Monthly time series counts for trend / anomaly checks
- Built visuals:
  - Heatmap of incident volume by crime type over time
  - Trend lines for selected high-volume categories
  - Simple anomaly detection (spikes vs rolling baseline)

## Key Outputs
- Heatmap: offense volume (rows) across time (columns)
- Trend chart: monthly incidents for selected crime types
- Summary tables: top crime categories and arrest-rate ranking

## Tech Stack
- Python: pandas, numpy, matplotlib
- SQL: SQLite (queried via pandas `read_sql_query`)
- Environment: Google Colab

## How to run
1. Open the notebook in Google Colab
2. Run all cells to:
   - ingest data into SQLite
   - execute SQL queries
   - generate charts and summary tables
