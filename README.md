# sql-data-warehouse-project
building a modern data warehouse with SQL servers including ETL Processing Data module and analysing
####################################################
# SQL Data Warehouse Project

## Project Overview

This repository documents my work on building a modern data warehouse using Microsoft SQL Server.

The project takes sales data from two source systems:

* CRM data
* ERP data

The data is extracted from CSV files, loaded into SQL Server, cleaned, standardised, integrated and prepared for reporting and analysis.

This project is based on the SQL Data Warehouse tutorial created by **Data With Baraa**. I am rebuilding the project myself to demonstrate my understanding of:

* Data warehouse design
* ETL processes
* SQL development
* Data cleaning
* Data integration
* Data modelling
* Data quality testing
* Project documentation
* Git and GitHub version control

---

## Project Status

> **Current status: In Progress**

I will update this README as I complete each stage of the project.

### Progress

* [x] Install SQL Server 2025 Express
* [x] Install and connect SQL Server Management Studio 22
* [x] Download the project CSV datasets
* [x] Create the GitHub repository
* [ ] Analyse the project requirements
* [ ] Design the data architecture
* [ ] Create the DataWarehouse database
* [ ] Build the Bronze layer
* [ ] Build the Silver layer
* [ ] Build the Gold layer
* [ ] Test data quality
* [ ] Complete project documentation
* [ ] Complete the final project review

---

## Project Objective

The objective of this project is to build a SQL data warehouse that combines sales information from CRM and ERP source systems.

The completed warehouse should provide clean, consistent and organised information that can be used for:

* Sales analysis
* Customer analysis
* Product analysis
* Business reporting
* Data-driven decision-making

---

## Project Requirements

The data warehouse will:

1. Import source data from CRM and ERP CSV files.
2. preserve the original source data in a raw layer.
3. Clean and standardise incorrect or inconsistent values.
4. Combine related data from the two source systems.
5. Create fact and dimension tables for analysis.
6. Check the quality and accuracy of the processed data.
7. Provide business-ready data for reports and dashboards.
8. Document the architecture, data flow and data model.

---

# Data Architecture

The project follows a three-layer data warehouse design:

```text
CRM CSV files ──┐
                ├──> Bronze Layer ──> Silver Layer ──> Gold Layer ──> Reports
ERP CSV files ──┘
```

The three layers are:

## 1. Bronze Layer — Raw Data

The Bronze layer stores the source data in its original form.

### Purpose

* Import CRM and ERP CSV files.
* Preserve the original source values.
* Keep a record of data received from each source system.
* Provide raw data for later processing.

### My understanding

The Bronze layer acts as the landing area of the warehouse. Very little transformation occurs here because the purpose is to preserve the source data before cleaning it.

### Planned work

* [ ] Create the `bronze` schema
* [ ] Create CRM source tables
* [ ] Create ERP source tables
* [ ] Load CRM CSV files
* [ ] Load ERP CSV files
* [ ] Create a Bronze loading procedure
* [ ] Check table row counts
* [ ] Record loading dates and errors

---

## 2. Silver Layer — Cleaned Data

The Silver layer contains cleaned, standardised and integrated data.

### Purpose

* Remove duplicate records.
* Correct invalid values.
* Standardise names, dates and codes.
* Handle missing information.
* Convert columns to appropriate data types.
* Combine related CRM and ERP information.
* Prepare reliable data for modelling.

### My understanding

The Silver layer improves data quality. Raw source information is transformed into consistent records that can be safely used by the Gold layer.

### Planned work

* [ ] Create the `silver` schema
* [ ] Create cleaned destination tables
* [ ] Remove unwanted spaces
* [ ] Standardise text values
* [ ] Standardise date values
* [ ] Replace invalid values
* [ ] Remove duplicates
* [ ] Match CRM and ERP records
* [ ] Create a Silver loading procedure
* [ ] Run data-quality tests

---

## 3. Gold Layer — Business Data

The Gold layer contains data prepared for reporting and analysis.

### Purpose

* Create business-friendly datasets.
* Organise information into facts and dimensions.
* Support analytical SQL queries.
* Make reporting easier and more reliable.

### My understanding

The Gold layer is the final presentation layer. It transforms the cleaned Silver data into a structure that business users and reporting tools can understand.

### Planned data model

```text
                 dim_customers
                       |
                       |
dim_products ──── fact_sales ──── dim_dates
```

### Planned Gold objects

* `gold.dim_customers`
* `gold.dim_products`
* `gold.fact_sales`

### Planned work

* [ ] Create the `gold` schema
* [ ] Create the customer dimension
* [ ] Create the product dimension
* [ ] Create the sales fact table or view
* [ ] Define primary and foreign-key relationships
* [ ] Validate fact-to-dimension relationships
* [ ] Test the final analytical model
* [ ] Create the star-schema diagram

---

# ETL Process

ETL means:

```text
Extract → Transform → Load
```

## Extract

Data is collected from the CRM and ERP CSV source files.

## Transform

The data is:

* Cleaned
* Standardised
* Validated
* Combined
* Restructured

## Load

The processed data is loaded into the appropriate SQL Server layer:

```text
Source files → Bronze → Silver → Gold
```

---

# Source Data

The project uses CSV files from two business systems.

## CRM Source

The CRM data contains information such as:

* Customers
* Products
* Sales transactions

## ERP Source

The ERP data contains additional information such as:

* Customer locations
* Customer birth dates
* Product categories

These sources must be integrated because related information may use different names, codes or formats.

---

# Tools Used

| Tool                            | Purpose                                                 |
| ------------------------------- | ------------------------------------------------------- |
| SQL Server 2025 Express         | Stores and processes the data warehouse                 |
| SQL Server Management Studio 22 | Creates databases, tables, views and SQL procedures     |
| CSV files                       | Provide the CRM and ERP source data                     |
| Draw.io                         | Creates architecture, data-flow and data-model diagrams |
| Git                             | Tracks changes made to the project                      |
| GitHub                          | Stores and presents the project repository              |
| Markdown                        | Documents the project in this README                    |

---

# Repository Structure

```text
sql-data-warehouse-project/
│
├── datasets/
│   ├── source_crm/
│   └── source_erp/
│
├── docs/
│   ├── data_architecture.drawio
│   ├── data_flow.drawio
│   ├── data_integration.drawio
│   └── data_model.drawio
│
├── scripts/
│   ├── init_database.sql
│   │
│   ├── bronze/
│   │   ├── ddl_bronze.sql
│   │   └── load_bronze.sql
│   │
│   ├── silver/
│   │   ├── ddl_silver.sql
│   │   └── load_silver.sql
│   │
│   └── gold/
│       └── ddl_gold.sql
│
├── tests/
│   ├── quality_checks_bronze.sql
│   ├── quality_checks_silver.sql
│   └── quality_checks_gold.sql
│
├── README.md
└── LICENSE
```

---

# Project Work Log

This section records what I completed and what I learned during each stage.

## Stage 1 — Project Preparation

### Work completed

* Installed SQL Server 2025 Express.
* Connected SSMS 22 to `LM2026\SQLEXPRESS01`.
* Downloaded the source datasets.
* Created the project folder.
* Created the GitHub repository.
* Reviewed the project requirements.

### What I learned

I learned that SQL Server is the database engine that stores and processes the data, while SSMS is the management application used to connect to the server and run SQL commands.

---

## Stage 2 — Data Architecture

### Work completed

*Add notes here after completing this section.*

### What I learned

*Add an explanation of why the Bronze, Silver and Gold layers are separated.*

---

## Stage 3 — Bronze Layer

### Work completed

*Add the tables, scripts and loading procedures that you create.*

### Problems encountered

*Record CSV import errors, incorrect paths or data-type problems here.*

### How I solved them

*Explain how you corrected each problem.*

### What I learned

*Explain what you learned about raw-data ingestion.*

---

## Stage 4 — Silver Layer

### Work completed

*Add the cleaning and transformation work completed here.*

### Data-quality problems found

Examples may include:

* Duplicate records
* Missing values
* Unwanted spaces
* Invalid dates
* Incorrect codes
* Inconsistent text
* Incorrect data types

### How I solved them

*Add the SQL functions and methods used to correct the data.*

### What I learned

*Explain why cleaning and standardisation are important.*

---

## Stage 5 — Gold Layer

### Work completed

*Add the fact tables, dimension tables or views created here.*

### What I learned

*Explain the purpose of dimensional modelling and a star schema.*

---

# Data-Quality Checks

I will use SQL queries to check:

* Duplicate primary keys
* Null values in required columns
* Invalid date ranges
* Invalid product costs
* Incorrect customer information
* Unmatched dimension records
* Broken relationships
* Incorrect sales calculations
* Unexpected row-count changes

Example:

```sql
SELECT
    customer_id,
    COUNT(*) AS duplicate_count
FROM silver.crm_cust_info
GROUP BY customer_id
HAVING COUNT(*) > 1;
```

---

# Example Business Questions

After completing the Gold layer, the warehouse should help answer questions such as:

1. How much revenue was generated?
2. Which products generated the most sales?
3. Which customers made the most purchases?
4. How have sales changed over time?
5. Which product categories perform best?
6. Which countries contain the most customers?
7. What is the average order value?
8. Are particular customer groups purchasing more products?

---

# Skills Demonstrated

This project demonstrates my ability to:

* Create SQL Server databases
* Design database schemas
* Create tables and views
* Import CSV data
* Write DDL and DML statements
* Build stored procedures
* Perform data cleaning
* Use SQL transformation functions
* Integrate multiple datasets
* Test data quality
* Build dimensional data models
* Create fact and dimension tables
* Document technical work
* Use Git and GitHub
* Explain my design decisions

---

# Challenges and Solutions

I will document important problems using this format:

## Challenge

Describe what went wrong.

## Cause

Explain why the problem occurred.

## Solution

Show how the problem was corrected.

## Lesson Learned

Explain how the experience improved my understanding.

---

# Project Results

This section will be completed after the project is finished.

The expected result is a working SQL Server data warehouse that:

* Loads CRM and ERP source files.
* Preserves raw source data.
* Cleans and integrates the information.
* Provides reliable analytical datasets.
* Uses a clear Bronze, Silver and Gold architecture.
* Supports reporting and business analysis.

---

# Author

**Name:** Leonaitasi Mafileo
**Project:** SQL Data Warehouse Project
**Status:** In Progress
**Database:** SQL Server 2025 Express
**Management Tool:** SQL Server Management Studio 22

---

# Acknowledgement

This learning project follows the SQL Data Warehouse tutorial and project structure created by **Data With Baraa**.

The SQL code, explanations and documentation in this repository represent my own work and understanding developed while following the tutorial.
