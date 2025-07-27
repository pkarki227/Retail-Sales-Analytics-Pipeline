# 🧩 Azure Retail Analytics Pipeline

An end-to-end **Retail Sales Analytics Pipeline** built on **Azure cloud technologies**, demonstrating modern **data engineering practices** from ingestion to dimensional modeling using:

- **Azure Data Factory (ADF)**
- **Azure Data Lake Storage Gen2 (ADLS Gen2)**
- **Azure Databricks**
- **dbt Cloud**

---

## 📌 Project Overview

This project simulates a real-world data engineering scenario where raw retail sales data is ingested, processed, cleaned, and modeled into a star schema for analytics.

---

## 🏗️ Architecture

mermaid graph TD
    A[GitHub CSV] --> B[Azure Data Factory]
    B --> C[ADLS Gen2 (raw)]
    C --> D[Azure Databricks]
    D --> E[ADLS Gen2 (processed)]
    E --> F[Databricks Tables]
    F --> G[dbt Cloud Models]
    G --> H[Dimensional & Fact Views]

## Tech Stack
| Component      | Technology                     |
| -------------- | ------------------------------ |
| Ingestion      | Azure Data Factory             |
| Storage        | ADLS Gen2                      |
| Processing     | Azure Databricks (PySpark)     |
| Transformation | dbt Cloud + Databricks         |
| Orchestration  | Manual (via notebooks/dbt run) |
| Output         | Star Schema (Views)            |


## Project Structure

azure-retail-analytics-pipeline/
│
├── data/
│   └── retail_sales_sample.csv         # Sample source data
│
├── adf/
│   └── azure_data_factory_pipeline.json  # ADF pipeline exported template
│
├── databricks/
│   └── notebooks/
│       ├── Data_Transformation_Raw_to_Processed.ipynb
│       └── managed_table_metastore.ipynb
│
├── dbt/
│   ├── models/
│   │   ├── staging/
│   │   │   └── stg_retail_sales.sql
│   │   ├── dimensions/
│   │   │   ├── dim_customers.sql
│   │   │   └── dim_products.sql
│   │   └── facts/
│   │       └── fact_sales.sql
│   ├── schema.yml
│   └── dbt_project.yml
│
└── README.md

## Data Model Summary
stg_retail_sales: Cleaned and structured base dataset from CSV

dim_customers: Extracted distinct customer info

dim_products: Categorized product info

fact_sales: Sales metrics and business KPIs



## Step-by-Step Guide
✅ Phase 1: Data Ingestion with ADF

    Create Linked Services for:

        GitHub (CSV source)

        ADLS Gen2 (sink)

    Build ADF pipeline to copy retail_sales_sample.csv → raw/ container

✅ Phase 2: Data Cleaning with Azure Databricks

    Mount or access ADLS Gen2 using abfss:// path

    Create and run notebook to:

        Read CSV from raw

        Clean nulls, fix types, format dates

        Write cleaned data → processed/ container

✅ Phase 3: Dimensional Modeling with dbt Cloud

    Set up dbt Cloud project

    Connect dbt → Azure Databricks using a SQL warehouse

    Configure:

        dbt_project.yml

        schema.yml

    Create and run models:

        stg_retail_sales.sql (base cleaned data)

        dim_customers.sql, dim_products.sql (dimensions)

        fact_sales.sql (aggregated KPIs)

    Run: dbt run to materialize views

## Output
All models are materialized as views in Databricks metastore under:

retailanalytics_dbricks3.retail_analytics

These views are now queryable from any BI or reporting tool connected to Databricks SQL.

