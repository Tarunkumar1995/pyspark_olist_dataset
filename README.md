Project Title
-------------
End-to-End Data Engineering Pipeline using PySpark & Databricks

Project Overview
----------------

This project shows how to build a production style data engineering pipeline on Databricks using PySpark.
The pipeline uses a layered (Bronze–Silver–Gold) architecture to take in raw data, change it, and make necessary transformations that are ready for analysis.


Olist E-Commerce Dataset 
------------------------
A real-world e-commerce dataset containing multiple related entities such as orders, customers, order items, and payments.
The dataset simulates transactional data typically ingested in production data pipelines.

Architecture
-------------

The project follows a layered data lake architecture.

Raw Source (CSV files)
   ↓
Bronze Layer (Parquet, schema enforced)
   ↓
Silver Layer (Cleaned & validated)   
   ↓
Gold Layer (Business metrics)        


Folder Structure
----------------

/Volumes/de_project_catalog/olist_bronze/
│
├── raw_source/           # Original CSV files (never modified)
│   ├── orders/
│   ├── customers/
│   ├── order_items/
│   └── payments/
│
├── bronze/               # Bronze layer output (Parquet)
│   ├── orders/
│   ├── customers/
│   ├── order_items/
│   └── payments/


Technologies Used
-----------------

* Databricks
* PySpark
* Apache Spark, 
* Parquet,
* Unity Catalog (Volumes & Schemas)


Bronze Layer Implementation
--------------------------
The Bronze layer is responsible for safe ingestion of raw data.

Key characteristics:
---------------------
* Explicit schema definitions (no inferSchema)
* Fault-tolerant ingestion using permissive mode
* Separation of raw source data and processed data
* Storage in Parquet format for performance and scalability
  
Notebooks
----------------------------------------------

| Notebook                   | Description                            |
| -------------------------- | -------------------------------------- |
| `00_environment_setup`     | Creates catalog, schemas, and volumes  |
| `01_bronze_data_ingestion` | Ingests raw CSV data into Bronze layer |

Key Engineering Practices Demonstrated
---------------------------------------
* Separation of raw and processed data
* Data ingestion using overwrite mode
* Schema enforcement during ingestion
* Production-style folder structure
* Re-runnable and scalable pipeline design
