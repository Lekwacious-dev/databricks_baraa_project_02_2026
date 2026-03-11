# Databricks_baraa_project_02_2026
## Data Engineering Medallion Architecture Pipeline
📌 Overview

This project implements a modern Data Engineering pipeline using the Medallion Architecture (Bronze → Silver → Gold) to transform raw data into analytics-ready business datasets.
---
## The pipeline is designed to ensure:
- Data reliability
- Data quality and standardization
- Scalable transformations
- Business-ready data modeling (Star Schema)
- Support for downstream analytics and reporting

---
## High Level Architecture
The architecture follows three core data layers
- Source Files → Bronze → Silver → Gold → Analytics / BI

---
## Bronze Layer — Raw Data
#### Purpose
Store raw ingested data exactly as received from source systems.

#### Characteristics
- 1:1 copy of source data
- No transformations
- Historical data preserved
- Used for auditing and reprocessing

#### Source Data
- CSV files
- External system extracts
- Landing storage volumes

#### Storage

- Delta Tables
- Unity Catalog managed storage

---
## Silver Layer — Clean & Standardized Data
#### Purpose
- Clean, standardize, and prepare data for modeling.
- Transformations
- Data type standardization
- Null handling
- Deduplication
- Data quality validation
- Schema enforcement

#### Characteristics
- Clean, trusted datasets
- No business logic or aggregations
- Ready for dimensional modeling

#### Storage
- Delta Tables
- Unity Catalog governed tables

---
## Gold Layer — Business Data
#### Purpose
Provide business-ready data for analytics and reporting.

#### Transformations
- Business rules applied
- Data modeling (Star Schema)
- Aggregations
- KPI calculations

#### Outputs
- Fact tables
- Dimension tables
- Aggregated business metrics

## Data Pipeline Flow
#### Ingestion
Raw data files are loaded into Bronze tables using notebooks or ingestion jobs.

#### Transformation
Notebooks transform data:
- Bronze → Silver (Cleaning & Standardization)
- Silver → Gold (Business Modeling)

#### Scheduling
- Pipeline runs daily
- Example schedule: 00:00 AM


## Technology Stack
| Component      | Technology                         |
| -------------- | ---------------------------------- |
| Processing     | PySpark / Spark SQL                |
| Storage        | Delta Lake                         |
| Governance     | Unity Catalog                      |
| Orchestration  | Notebook Jobs / Workflow Scheduler |
| Cloud Platform | Databricks                         |
| Languages      | Python, SQL                        |


## Business Value

This architecture enables:
- Reliable reporting datasets
- Scalable data processing
- Faster query performance
- Centralized business logic
- Regulatory compliance readiness