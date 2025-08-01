# Data Warehousing
NY Metro Authority Lakehouse Platform  

## Overview  
This project builds a modern Lakehouse platform for the NY Metro Authority using Snowflake, dbt, and Power BI. It ingests and models ridership, delay, and remote sensor data across six subway stops during January 2024. The solution supports five key business processes and enables interactive KPI tracking through dimensional modeling, ELT workflows, and dashboard development.

## Table of Contents  
- Introduction  
- Dataset Description  
- Architecture  
- Methods  
  - Step 1: Data Ingestion  
  - Step 2: Data Modeling (Staging → ODS → DWH)  
  - Step 3: dbt Testing and Documentation  
  - Step 4: Dashboard Design  
- Results and Evaluation  
- Conclusion  

## Introduction  
The goal is to design a scalable analytics solution for transit operations. Using a star schema and conformed dimensions, the platform enables stakeholders to analyze peak/off-peak rider trends, delay patterns, unit battery health, and customer behavior—all in one integrated system.

Key aspects of the project include:  
- Scalable ELT pipelines using Snowflake and dbt  
- Dimensional modeling for multiple business processes  
- Data governance via dbt testing and documentation  
- Power BI dashboard for stakeholder insights  

## Dataset Description  
The source includes CSV files capturing events from 6 subway stations for January 2024.  

- **Rider Data**: Entry/exit timestamps, route codes  
- **Unit Data**: Battery health, location pings  
- **Line Performance**: On-time %, delays, route ID  
- Total rows: ~10,000 | Columns: ~10+ attributes  

## Architecture  
The project follows a multi-layer Lakehouse design:  

- **Staging**: Raw-to-clean data transformations  
- **ODS (Operational Data Store)**: Business rule application  
- **DWH (Data Warehouse)**: Dimensional tables for analytics  

Key Dimensions: `dim_time`, `dim_stops`, `dim_lines`, `dim_remote_units`  
Fact Tables: `fact_rider_volume`, `fact_line_performance`, `fact_remote_monitor`, etc.  

## Methods  

### Step 1: Data Ingestion  
- Loaded CSVs into Snowflake using external stages  
- Created raw → staging models via dbt  

### Step 2: Data Modeling  
- Developed clean, tested staging and ODS models  
- Implemented a star schema with conformed dimensions  
- Defined fact tables for each core process  

### Step 3: dbt Testing and Documentation  
- Added schema and data tests (not_null, unique, relationships)  
- Generated model documentation and lineage graphs  

### Step 4: Dashboard Design  
- Created Power BI dashboard with real-time metrics  
- Visuals included ridership heatmaps, stop performance, and unit health  

## Results and Evaluation  

### Data Layer  
- Fully functional Lakehouse stack with Snowflake + dbt  
- 100% dbt test coverage for all models  
- Models reusable for incremental loads and joins  

### Dashboard Layer  
- Interactive KPI views for rider volume, delays, battery alerts  
- Supports time-based filtering and drill-downs  
- Enables transit ops and planning teams to make data-driven decisions  

## Conclusion  
This project successfully implements an end-to-end data engineering pipeline for NY Metro Authority. It showcases strong ETL, modeling, and dashboarding skills using modern cloud tools. The system improves data accessibility and provides actionable insights to support operational efficiency and rider satisfaction.
