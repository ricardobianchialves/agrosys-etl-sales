# Agrosys ETL → Power BI

Python pipeline that extracts sales data from the Agrosys ERP via ODBC, consolidates 5 Data Warehouse tables, and exports a clean dataset to feed a Power BI dashboard.

## Problem

Manually updating sales data (extracting and organizing it in Excel) used to take about **1 hour**.

## Solution

A notebook that:
1. Connects directly to the ERP's Data Warehouse via ODBC
2. Extracts the invoice items, invoice header, product registry, customer, and city tables
3. Selects only the relevant columns
4. Consolidates everything through merges (equivalent to Excel's VLOOKUP/XLOOKUP)
5. Creates year and month columns for easier time-based analysis
6. Exports the final result to Excel, ready to be consumed by Power BI

## Result

Update time reduced from **1 hour to less than 5 minutes**.

## Tech stack

- Python
- pandas
- pyodbc
- SQL

## How to use

1. Clone this repository
2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Create a `.env` file in the project root with your credentials (use `.env.example` as a template)
4. Run the notebook `agrosys_etl_pipeline.ipynb`

## Note

Database credentials are **not** in the code — they are loaded from environment variables (a `.env` file, which is not version-controlled).

## Dashboard Preview
![Power BI Dashboard](dashboard_preview.png)
