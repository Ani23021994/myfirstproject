End-to-End Azure Databricks Data Engineering Pipeline
This repository contains the complete implementation of a production-ready, end-to-end data engineering pipeline using Azure Databricks, Delta Lake, and Data Factory. The project implements a modern Medallion Architecture to ingest, transform, and serve enterprise data for downstream analytics.
📌 Architecture Overview
The project processes raw source data through three distinct layers within Delta Lake:
[Raw Sources] ──> 📦 Bronze (Ingestion) ──> ⚙️ Silver (Enrichment) ──> 📊 Gold (Aggregation) ──> [Power BI / BI Tools]
Bronze Layer: Raw data ingestion from source systems with minimal schema enforcement.
Silver Layer: Data cleaning, deduplication, schema validation, and enrichment.
Gold Layer: Business aggregates, star-schema dimensional modeling, and analytical views.
🚀 Key Features
Medallion Design: Structured data evolution using Delta Lake ACID transactions.
Auto Loader: Scalable incremental file ingestion from cloud storage using cloudFiles.
Unity Catalog: Centralized data governance, lineage tracking, and access control.
CI/CD Pipeline: Automated deployment using GitHub Actions and Databricks Asset Bundles (DABs).
Orchestration: Multi-task workflows managed via Databricks Workflows and Azure Data Factory.
📁 Repository Structure

├── .github/workflows/      # CI/CD deployment pipelines
├── databricks.yml          # Databricks Asset Bundle (DAB) configuration
├── src/
│   ├── notebooks/          # Databricks Notebooks
│   │   ├── 01_bronze/      # Raw ingestion and Auto Loader scripts
│   │   ├── 02_silver/      # Data cleaning and transformation
│   │   └── 03_gold/        # Business logic and gold table generation
│   ├── dbt/                # Optional: dbt models if used for transformation
│   └── shared/             # Common utilities, logging, and helpers
├── tests/                  # Unit and integration tests (pytest-spark)
└── README.md               # Project documentation
