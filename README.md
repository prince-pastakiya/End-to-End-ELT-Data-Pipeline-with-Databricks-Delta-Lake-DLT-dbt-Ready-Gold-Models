# 🚀 End-to-End ELT Data Pipeline on Databricks

A production-style **ELT data engineering pipeline** built using **Databricks, Delta Lake, Delta Live Tables (DLT), and PySpark**, designed with **incremental ingestion, CDC-based transformations, and reusable Gold-layer models**.

This project demonstrates how raw data can be ingested, validated, transformed, and modeled into **analytics-ready dimension and fact tables**, following modern data engineering best practices.

---

## 📌 Project Overview

This project implements a **multi-layer ELT architecture**:

- **Bronze Layer**: Incremental ingestion of raw CSV files using Databricks Auto Loader  
- **Silver Layer**: Streaming CDC processing with Delta Live Tables (DLT) and data quality rules  
- **Gold Layer**: Reusable, parameter-driven dimension and fact table creation using Delta Lake MERGE  

The design is **dynamic and reusable**, allowing new datasets to be onboarded with minimal configuration changes.

---

## 🏗️ Architecture

Raw CSV Files
   ↓
Bronze Layer (Auto Loader, Delta)
   ↓
Silver Layer (DLT, CDC, Data Quality)
   ↓
Gold Layer (Dimensions & Facts)
   ↓
Analytics / BI / dbt

---

## 🧱 Data Layers

### 🟤 Bronze Layer
- Incremental ingestion using **Databricks Auto Loader**
- Schema inference with rescue mode
- Raw data stored as Delta tables
- Parameter-driven ingestion for multiple datasets

**Notebook:** `BronzeLayer.ipynb`

---

### ⚪ Silver Layer
- Built using **Delta Live Tables (DLT)**
- Streaming ingestion from Bronze
- CDC handling using `create_auto_cdc_flow`
- SCD Type 1 processing
- Data quality enforcement using `dlt.expect_all_or_drop`

**Pipeline:** `Pipeline.py`

---

### 🟡 Gold Layer
- Analytics-ready **star schema**
- Reusable **SCD Type 1 dimension framework**
- Dynamic fact table generation
- Surrogate key creation
- Incremental UPSERT logic using Delta MERGE
- dbt-compatible modeling approach

**Notebooks:**
- `Gold_Dims.ipynb`
- `Gold_Fact_Table.ipynb`

---

## ⚙️ Key Features

- Incremental data ingestion (no full reloads)
- CDC-based transformations
- Delta Lake MERGE for UPSERTs
- Streaming + batch hybrid processing
- Parameter-driven and reusable notebooks
- Data quality validation
- Enterprise-style dimensional modeling

---

## 🔁 Dynamic & Reusable Design

This pipeline is **configuration-driven**, not hardcoded.

By changing parameters such as:
- source table name
- business key columns
- CDC column
- target object name

…the same notebooks can be reused to build **new dimensions and fact tables** for different datasets.

---

## 🧪 Example Use Cases

- Flight and booking analytics
- Customer and passenger dimensions
- Airport and reference data modeling
- Finance or transactional analytics
- Foundations for dbt transformations

---

## 🧰 Tech Stack

- Databricks
- Apache Spark (PySpark & SQL)
- Delta Lake
- Delta Live Tables (DLT)
- Databricks Auto Loader
- Streaming CDC
- dbt-ready Gold models

---

## 📂 Project Structure

├── notebooks/
│ ├── Setup.ipynb
│ ├── BronzeLayer.ipynb
│ ├── Gold_Dims.ipynb
│ ├── Gold_Fact_Table.ipynb
│
├── pipelines/
│ └── Pipeline.py
│
├── README.md

---

## 🚀 How to Run

1. Run `Setup.ipynb` to create schemas and volumes  
2. Ingest raw data using `BronzeLayer.ipynb`  
3. Deploy the DLT pipeline using `Pipeline.py`  
4. Create Gold dimensions using `Gold_Dims.ipynb`  
5. Create Gold fact tables using `Gold_Fact_Table.ipynb`  

---

## 🎯 What This Project Demonstrates

- Real-world data engineering workflows
- Incremental ELT design
- CDC-based data processing
- Delta Lake best practices
- Reusable and scalable pipeline design
- Production-oriented thinking

---

## 📈 Future Enhancements

- SCD Type 2 support
- Advanced data quality metrics
- dbt models on top of Gold layer
- Monitoring and alerting
- Performance optimization at scale

---

## 👤 Author

**Prince Pastakiya**  
Data Engineer | Databricks | Spark | Delta Lake
