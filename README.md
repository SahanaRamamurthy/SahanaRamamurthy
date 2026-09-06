# Hi, I'm Sahana Ramamurthy 👋

🎓 Master of Data Science @ RMIT University &nbsp;|&nbsp; 📍 Melbourne, Australia  
🔍 Turning raw data into decisions that actually matter

## About Me

I'm a data professional with a passion for building things end-to-end — not just analysing data, but engineering the pipelines, warehouses, and orchestration that bring it to life. My recent focus has been full-stack data engineering: building Medallion-architecture lakehouses on Databricks with dbt, wiring up incremental and SCD-tracked pipelines, and orchestrating the whole thing with Airflow in Docker.

My background spans **Data Analyst at Capgemini**, a **Data Science internship at Australian Red Cross Lifeblood**, a **Data Engineer role at ORL Reports (ConsultDoc)**, and a **Master of Data Science at RMIT**, giving me a rare mix of technical depth and business thinking.

I work across the full data stack:
- **Engineering** Medallion-architecture lakehouses, incremental dbt pipelines, SCD2 dimensional models, and Airflow-orchestrated workflows
- **Building** ETL pipelines, REST APIs, relational databases, and automated workflows
- **Analysing** revenue diagnostics, fraud detection, compliance risk, and credit risk
- **Communicating** through interactive dashboards, stakeholder reporting, and clear visual storytelling

## Tech Stack

**Data Engineering:** &nbsp; Databricks (SQL Warehouse & Unity Catalog) · dbt-core · dbt-databricks · dbt_utils · Apache Airflow · Docker & Docker Compose · Medallion Architecture (Bronze/Silver/Gold) · Incremental Models · SCD Type 2 Dimensional Modeling · Star Schema Design · Data Lineage · Data Quality Testing · Delta Lake · Agentic DB

**Languages:** &nbsp; Python · SQL · R · C · C++ · JavaScript · HTML · CSS · Astro

**Data & ML:** &nbsp; Pandas · NumPy · Scikit-learn · Gradient Boosting · Logistic Regression · Deep Learning · Neural Networks · NLP · Computer Vision · TF-IDF · RAG Pipelines · Feature Engineering · EDA · Time Series Analysis · Statistical Analysis · Hypothesis Testing

**Big Data:** &nbsp; Apache Spark · Hadoop

**Backend & APIs:** &nbsp; Flask · FastAPI · SQLAlchemy · REST APIs · OpenAI API · Claude AI

**Databases:** &nbsp; Google BigQuery · PostgreSQL · MySQL · SQLite

**Visualisation:** &nbsp; Power BI · Plotly · Plotly Dash · Tableau · Chart.js · MS Excel · openpyxl

**Tools & Platforms:** &nbsp; Docker · Kubernetes · Git · Microsoft 365 · Azure · Google Cloud Platform · Anaconda · MYOB

**Domain Knowledge:** &nbsp; Credit Risk (PD · LGD · EAD) · APRA Regulation · Basel III · IRB Modelling · Stress Testing · Fraud Detection · Regulatory Compliance

## Featured Projects

### 🏗️ Walmart Retail Data Platform — Medallion Lakehouse on Databricks
> *End-to-end data engineering: Bronze → Silver → Gold on Databricks, orchestrated with Airflow in Docker*

🔗 [View Project](https://github.com/SahanaRamamurthy/MYDATAJOURNEY)

A retail data platform built the way I'd build it as a data engineer on the job — incremental loads instead of full reloads, tested transformations, historical tracking of dimension changes, and an orchestrator that runs the whole pipeline on a schedule without manual intervention.

- Designed a 3-layer **Medallion architecture** (Bronze → Silver → Gold) on **Databricks Unity Catalog**, turning raw operational data into analytics-ready, business-consumable tables
- Built **6 incremental dbt models** using a watermark-based freshness pattern (`MAX(updated_timestamp)`), keeping reprocessing cost flat as data volume grows instead of re-scanning the full source every run
- Engineered a **wide "One Big Table"** denormalization layer via Jinja-templated dynamic joins, pre-joining six source entities once so every downstream Gold model reads from a single simplified source
- Implemented **SCD Type 2 dimension snapshots** (5 dimensions) with dbt's timestamp strategy, enabling accurate historical reporting against the dimension values that were true *at the time* of each transaction — not just today's values
- Built a **Kimball-style star schema** (`fact_orders` + 5 SCD2 dimensions) as the business-consumable analytics layer
- Wrote **schema and singular data quality tests** (`not_null`, `unique`, `dbt_utils.accepted_range`) to guard the pipeline against bad joins and invalid data
- Containerized a full **Apache Airflow orchestration environment** (Docker Compose, custom image with dbt baked in) chaining the pipeline end-to-end: source freshness check → `dbt run` → `dbt test` → `dbt snapshot`
- Debugged and resolved real production-style issues along the way: profile/schema misconfigurations, incremental SQL bugs, join fan-out row explosions, and Airflow DAG import errors

`dbt-core` `dbt-databricks` `Databricks` `Apache Airflow` `Docker` `SQL` `Python` `Medallion Architecture` `SCD Type 2` `Unity Catalog`

### 🏦 Mortgage Credit Risk Analytics
> *End-to-end credit risk analytics: IRB modelling, APRA compliance, live BigQuery dashboard*

🔗 [View Project](https://github.com/SahanaRamamurthy/Mortgage-credit-risk-analytics)

A production-grade mortgage portfolio risk analytics system built to demonstrate the full analyst workflow at a major Australian bank, from raw data generation to regulatory reporting and a live interactive dashboard.

- Engineered a synthetic Australian mortgage portfolio of **10,000 loans (~AUD 5.3B exposure)** with realistic state-level property values, RBA rate cycles, and credit distributions
- Built credit risk models using the **IRB approach** with Logistic Regression scorecard and Gradient Boosting challenger for PD, LGD, and EAD estimation (AUC: 0.82)
- Ran **4-scenario stress tests** (Base, Mild, Moderate, GFC) against property price shocks, rate shocks, and income shocks, quantifying Expected Loss impact up to AUD 85M
- Wrote **15 analytical SQL queries** covering APRA APS 112 capital requirements, Basel III risk-weighted assets, serviceability buffers, vintage analysis, and NPL waterfall
- Built a **cross-filter interactive dashboard** in Plotly Dash where clicking any chart element updates all 10 panels instantly, powered live by **Google BigQuery**
- Delivered a formatted **Excel reporting workbook** with RAG KPI scorecards, embedded charts, and credit band risk profiles

`Python` `SQL` `Google BigQuery` `Plotly Dash` `Scikit-learn` `openpyxl` `APRA` `Basel III` `IRB`

### 🚗 Car Insurance Data Migration Platform
> *End-to-end data engineering: from messy CSVs to a live analytics dashboard*

🔗 [View Project](https://github.com/SahanaRamamurthy/CarInsurance-DataMigration_Platform)

Built a complete data migration system simulating what a real insurance company faces when modernising its data infrastructure.

- Designed and ran a full ETL pipeline across 5 datasets, resolving mixed date formats, inconsistent values, currency strings, and missing data into a normalised PostgreSQL relational schema
- Built 10 REST API endpoints surfacing fraud detection, high-risk customer identification, late payment tracking, and migration health metrics
- Delivered an interactive analytics dashboard with dark/light theme toggle, live charts, and vehicle lookup
- Containerised with Docker Compose and wrote production-ready Kubernetes manifests for cloud deployment

`Python` `Flask` `PostgreSQL` `SQLAlchemy` `Docker` `Kubernetes` `Pandas` `Chart.js`

### 🏥 HealthFirst Australia: Revenue Intelligence System
> *Diagnosed a 15% revenue decline and built a machine learning churn model*

🔗 [View Project](https://github.com/SahanaRamamurthy/Healthcare-Revenue-Analytics)

A full analytics engagement from problem statement to recommendation, the kind of work that directly shapes business decisions.

- Diagnosed a 15% revenue decline across 3,000 patients and 20,000 appointments, tracing root cause to Medicare bulk billing gaps
- Trained a Gradient Boosting churn model to identify at-risk patients before they disengage
- Segmented patients into 7 RFV (Recency, Frequency, Value) tiers for targeted retention strategy
- Delivered a fully self-contained interactive Plotly dashboard with no server required, shareable as a single HTML file

`Python` `Scikit-learn` `Gradient Boosting` `Plotly` `Pandas` `Machine Learning`

## Experience

**IT Service Desk Analyst** at Lincom Consulting *(May 2026 to Present)*  
**Data Engineer** at ORL Reports Pty Ltd / ConsultDoc *(Nov 2025 to Apr 2026)*  
**Data Science Intern** at Australian Red Cross Lifeblood *(Aug 2025 to Nov 2025)*  
**Medical Office Administrator** at ORL Reports Pty Ltd *(Oct 2024 to Nov 2025)*  
**Data Analyst** at Capgemini *(Aug 2022 to Jan 2024)*

## Certifications

- 🏅 Microsoft Azure Fundamentals (AZ-900)
- 🏅 Problem Solving Through Programming in C, NPTEL

## Let's Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Sahana%20Ramamurthy-0077B5?style=for-the-badge&logo=linkedin)](https://linkedin.com/in/sahana-ramamurthy-9640b51a5)
[![GitHub](https://img.shields.io/badge/GitHub-SahanaRamamurthy-181717?style=for-the-badge&logo=github)](https://github.com/SahanaRamamurthy)
[![Email](https://img.shields.io/badge/Email-sahana42ramamurthy@gmail.com-D14836?style=for-the-badge&logo=gmail)](mailto:sahana42ramamurthy@gmail.com)
