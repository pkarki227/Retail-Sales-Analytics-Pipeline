# Case Study: Retail Analytics Pipeline on Azure

## 🌍 Overview

Designed and implemented an end-to-end **Retail Analytics Data Engineering Project** using **Azure Cloud**, **Databricks**, and **dbt Cloud**, simulating real-world enterprise pipelines for retail sales data. The project was aimed at building robust, scalable, and modular cloud-native analytics infrastructure.

---

## 📊 Goal

To deliver a cloud-based pipeline that:

- Ingests and processes raw sales data.
- Cleans and transforms data into a structured star schema.
- Supports BI & advanced analytics.

---

## 🚀 Architecture

```
Azure Data Factory (ADF)
  └→ Raw CSV ➔ ADLS Gen2 (Raw Zone)
      └➔ Azure Databricks Notebook (Transformations)
          └➔ ADLS Gen2 (Processed Zone)
              └➔ dbt Cloud (Staging, Fact, Dim Models)
                  └➔ Star Schema in Hive Metastore
                      └➔ Power BI / SQL Analytics Ready
```

---

## ✅ Key Steps

### Phase 1: Data Ingestion

- Used **Azure Data Factory** to ingest CSV data into **ADLS Gen2** `raw/` container.
- Created pipeline with Copy Activity & parameterization for extensibility.

### Phase 2: Data Cleaning (Databricks)

- Cleaned `retail_sales_data.csv` in Azure **Databricks Notebooks**.
- Wrote cleaned output into ADLS Gen2 `processed/` container as `retail_sales_cleaned.csv`.

### Phase 3: Transformation & Modeling (dbt Cloud)

- Connected **dbt Cloud** to Databricks via Service Principal.
- Created:
  - `stg_retail_sales.sql`: selects from `retail_sales_cleaned`
  - `dim_customers.sql` & `dim_products.sql`
  - `fact_sales.sql`
- Used **schema.yml** to define sources & tests.
- Configured `dbt_project.yml` with cloud catalog/schema.

---

## 🤝 Skills Demonstrated

- Azure Data Factory (ADF)
- Azure Databricks (DataFrames, ABFSS access)
- Azure Data Lake Gen2 (Storage)
- dbt Cloud (Models, Sources, Cataloging)
- SQL & Python (PySpark)
- Star Schema Design (Dimensional Modeling)
- Cloud IAM (App Registration & Secrets)
- GitHub Project Documentation

---


## 💼 Use Cases

- Retail BI Dashboards (Power BI, Databricks SQL)
- Customer Segmentation
- Product Sales Trend Analysis
- Foundation for ML Feature Engineering

---

## ✨ Outcome

This project demonstrates real-world capabilities in building a **modular data lakehouse pipeline** with cloud services. It is production-scalable, modular, and extensible for analytics, machine learning, and dashboarding.

---

**GitHub Repo**: [github.com/pkarki227/azure-retail-analytics-pipeline](https://github.com/pkarki227/azure-retail-analytics-pipeline)

**Contact**: [pawankarki227@gmail.com](mailto\:pawankarki227@gmail.com)

