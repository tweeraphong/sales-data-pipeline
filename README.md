
# Sales Data Pipeline (Portfolio Project)

## Overview
This project demonstrates a simple **Data Engineering pipeline** that processes raw sales data and prepares it for analytics and dashboards.

The pipeline performs:
- Data extraction from raw CSV
- Data transformation and cleaning
- Data validation and quality checks
- Data loading into processed datasets
- Logging and monitoring

This project simulates a real‑world workflow used by **Data Engineers** to prepare datasets for analytics platforms such as Power BI or Tableau.

---

## Architecture

+----------------------+
|      Raw Data        |
|   raw_sales.csv      |
|   data/raw/          |
+----------+-----------+
           |
           v
+----------------------+
|       Extract        |
|   Read CSV (Pandas)  |
+----------+-----------+
           |
           v
+----------------------+
|      Transform       |
| Clean data           |
| Remove duplicates    |
| Handle missing data  |
+----------+-----------+
           |
           v
+----------------------+
|       Validate       |
| Data quality checks  |
| Schema validation    |
| Negative values      |
| Date validation      |
+----------+-----------+
           |
           v
+----------------------+
|         Load         |
| Write to Database    |
| (PostgreSQL/SQLite)  |
+----------+-----------+
           |
           v
+----------------------+
|   Analytics Layer    |
| Power BI Dashboard   |
+----------------------+

---

## Project Structure

sales-data-pipeline
│
├── data
│   ├── raw
│   │   └── raw_sales.csv
│   │
│   └── processed
│       └── clean_sales.csv
│
├── pipeline
│   ├── extract.py
│   ├── transform.py
│   ├── validate.py
│   ├── load.py
│   └── logger.py
│
├── logs
│   └── pipeline.log
│
├── dashboard
│   └── sales_dashboard.pbix
│
└── run_pipeline.py

---

## Dataset

The test dataset contains **5,000 sales records** including:

- order_id
- date
- product
- region
- channel
- quantity
- unit_price
- sales

Intentional data issues were added for testing:

- Missing values
- Negative sales values
- Random data distribution

This allows the pipeline's **validation step** to detect and log data quality problems.

---

## Technology Stack

Python  
Pandas  
CSV Data Storage  
Logging Module  
Power BI (Dashboard)

---

## How to Run

Run the pipeline:

python run_pipeline.py

The pipeline will:

1. Extract raw sales data
2. Transform and clean records
3. Validate dataset quality
4. Load processed data to `/data/processed`
5. Log execution details

---

## Example Log Output

INFO - Pipeline started  
INFO - Extract completed (5000 rows)  
INFO - Transform completed  
INFO - Validation completed  
INFO - Load completed  
INFO - Pipeline finished  

---

## Dashboard

The processed dataset can be visualized in Power BI showing:

- Sales by product
- Sales by region
- Monthly sales trends

---

## Author

Portfolio project demonstrating **Data Engineering fundamentals** including ETL pipeline design, data validation, and logging.
