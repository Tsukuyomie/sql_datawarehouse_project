Data Warehouse Architecture – Bronze, Silver, Gold Layers

**Overview**
This project demonstrates a modern data warehouse architecture using a three-layer design (Bronze, Silver, Gold). It shows how raw data from different source systems is processed, cleaned, and transformed into business-ready datasets for reporting, analytics, and machine learning.

Architecture Summary
1. Sources

Data comes from multiple systems such as CRM and ERP.
Data format: CSV files stored in folders.
Data is loaded into SQL Server for further processing.

2. Bronze Layer – Raw Data

Purpose: Store raw, unprocessed data as-is from the source.
Object Type: Tables
Load Method: Batch Processing, Full Load, Truncate & Insert
No transformations are performed at this stage.
Data Model: None (as-is)

3. Silver Layer – Cleaned & Standardized Data

Purpose: Convert raw data into a clean, consistent, and standardized format.
Object Type: Tables
Load Method: Batch Processing, Full Load, Truncate & Insert
Transformations: Data Cleansing, Data Standardization, Data Normalization, Derived Columns, Data Enrichment
Data Model: None (as-is)

4. Gold Layer – Business-Ready Data

Purpose: Provide analytics-ready data for BI, reporting, and machine learning.
Object Type: Views
No load required — uses transformations from Silver Layer.
Transformations: Data Integration, Aggregation, Business Logic
Data Model: Star Schema, Flat Tables, Aggregated Tables

5. Consumption Layer

Consumers of Gold Layer data include:
BI & Reporting tools (Power BI, Tableau)
Ad-hoc SQL queries
Machine Learning models


**Tech Stack**

Database: SQL Server
Scripting: Stored Procedures
Data Format: CSV
Tools: Power BI / Tableau for visualization

🚀 How It Works

Raw CSV files are dropped into source folders.
Data is loaded into the Bronze Layer using stored procedures.
The Silver Layer cleans and standardizes the data.
The Gold Layer applies business rules to prepare analytics-ready views.
End-users access the Gold Layer via BI tools or SQL queries.
