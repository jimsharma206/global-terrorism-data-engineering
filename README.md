# global-terrorism-data-engineering
ETL pipeline built with Azure Data Factory, SQL, and Blob Storage to clean and visualize global terrorism data

# Global Terrorism Data Pipeline (1970–2011)

This project demonstrates a real-world ETL pipeline using Azure services to ingest, clean, store, and visualize the Global Terrorism Dataset.

## 🚀 Overview
We extract raw CSV data from Azure Blob Storage, transform and clean it using Azure Data Factory (ADF), and load it into Azure SQL Database for analysis in Tableau and Power BI.

## 🏗️ Architecture

Azure Blob Storage
(Raw GTD CSV file)
        ↓
Azure Data Factory Pipeline
  - Copy Activity
  - Fault Tolerance Enabled
        ↓
Azure SQL Database
  Table: dbo.GTD_Events
        ↓
Tableau Public + Power BI
  - Geospatial Map
  - Animated by Year


## 🧱 Tools Used
- **Azure Data Factory**
- **Azure Blob Storage**
- **Azure SQL Database**
- **Power BI**
- **Tableau Public**
- **SQL** (DDL + queries)
- **GitHub** (for documentation)

## 📁 Key Files
- `ADF_GTD_CopyPipeline.json` — exported pipeline JSON
- `schema.sql` — CREATE TABLE script for `GTD_Events`
- `dashboard.png` — Tableau or Power BI screenshot
- `README.md` — project documentation

## 📊 Dashboard (Tableau)
[View Animated Global Attack Map (1970–2011)](https://public.tableau.com/app/profile/james.sharma8234/viz/DecadesofTerrorGlobalTerrorismVisualization19702011/Dashboard1)

## 📌 Features
- Fault-tolerant pipeline with skipped malformed rows
- Manually mapped CSV → SQL columns
- Clean schema-based loading into SQL
- Interactive map + year slider visualization

## 📈 Sample Query
```sql
SELECT region_txt, COUNT(*) AS attack_count
FROM dbo.GTD_Events
GROUP BY region_txt
ORDER BY attack_count DESC;

