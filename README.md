# Capstone Project: Retail Sales Pipeline

This project implements a three-layer Lakehouse data pipeline (Bronze, Silver, Gold) for a simulated retail sales environment.

## Architecture Overview

- **Bronze Layer**: Ingests streaming JSON sales data using Databricks AutoLoader
- **Silver Layer**: Cleans and joins the sales fact with customer, product, and date dimension tables (sourced from MongoDB and Azure SQL)
- **Gold Layer**: Aggregates product-level metrics (total sales, revenue, and price), saved as a Delta table and queried via SQL

## Data Sources

- `sales_fact*.json` (streaming input)
- `customer_dim` from MongoDB Atlas
- `product_dim`, `dim_date` from Azure SQL Database

## Files Included

- `Customer_Dim_Import.ipynb` — final notebook with pipeline
- `/data/` folder with sample `sales_fact*.json`

## How to Run

1. Upload the notebook to Databricks
2. Ensure MongoDB and Azure SQL credentials are connected
3. Re-upload `sales_fact` files to `/FileStore/streaming/sales_fact/`
4. Re-run each notebook section in order (Bronze → Silver → Gold)

---

## Author

Eshal Farooq
