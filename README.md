# Azure Healthcare Supply Chain Analytics Platform

## Project Overview
This project demonstrates an end-to-end cloud-based healthcare analytics platform built using Azure services, SQL, and Power BI to analyze hospital inventory, operational, and supply chain data.

## Business Problem
Hospitals often struggle with inventory visibility, operational efficiency, procurement monitoring, and resource utilization across departments. This project centralizes healthcare operational data into a scalable analytics platform to provide KPI-driven insights and executive reporting.

## Tech Stack
- Azure Blob Storage
- Azure Data Factory
- Azure SQL Database
- Databricks
- SQL
- Power BI
- GitHub

## Architecture
CSV Files → Azure Blob Storage → Azure Data Factory → Azure SQL Database → Power BI Dashboard

## Project Goals
- Build cloud-based ETL pipelines
- Design SQL transformation layers
- Create analytics-ready datasets
- Develop KPI dashboards
- Demonstrate Analytics Engineering concepts

## Dataset Features

Hospital Inventory dataset includes:
- Item details
- Supplier information
- Quantity and stock levels
- Expiry dates (mixed formats in raw data)
- Department-wise distribution

⚠️ Data Challenges Handled

During pipeline development, multiple real-world issues were encountered and resolved:
- Mixed date formats (21-03-2026, 5/8/2026)
- Missing and null values in source data
- Extra/blank columns in Excel files
- Schema mismatches between source and sink
- Column naming conflicts in Data Flow output
- Type conversion failures during loading into SQL

🔄 Transformations Applied
- Using Mapping Data Flow in ADF:
- Derived Column transformation for date standardization
toDate(expiry_date, 'dd-MM-yyyy')
- Null handling using conditional expressions
- Schema alignment between source and sink
- Column renaming and mapping corrections
Data type conversion (String → DateTime)

🧪 Pipeline Workflow
- Raw data uploaded to Azure Blob Storage
- ADF Copy Activity ingests raw data
- Mapping Data Flow performs transformations
- Data validation and schema correction applied
- Clean data loaded into Azure SQL Database
- Pipeline executed via Trigger Run successfully

🐞 Issues Resolved
- TypeConversionFailure due to mixed date formats
- DelimitedTextColumnNameNotAllowNull caused by empty Excel headers
- SqlColumnNameNotExist due to mapping mismatch
- Data Flow debugging and schema refresh issues
- Column naming conflicts (clean-expiry_date vs expiry_date)

📈 Key Learnings
- Real-world data is messy and requires multiple validation layers
- ADF Data Flows are powerful but limited for complex parsing logic
- Schema consistency is critical in ETL pipelines
- Debugging is a core skill in data engineering workflows
- Importance of staging and transformation layers in cloud pipelines

🏆 Final Outcome
- Fully functional ETL pipeline built in Azure
- Clean and structured hospital inventory data in SQL Database
- Successfully handled real-world data quality issues
- Production-like pipeline with transformation and validation logic

🔮 Future Enhancements
- Implement Bronze → Silver → Gold architecture
- Add data quality validation layer (reject bad records)
- Build Power BI dashboard for analytics
- Automate pipeline scheduling (daily refresh)
- Integrate Databricks for advanced transformations

👩‍💻 Author
Anusha Komati
@ Senior Data Analyst | Aspiring Data Engineer
@ skills: SQL, Power BI, Tableau, Python, Azure Data Factory

⭐ If you like this project
Feel free to ⭐ the repo and connect on LinkedIn!
