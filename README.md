# DW Migration Pipeline

ETL pipeline migrating a star schema database from SQL Server to PostgresSQL - with pre/post validation and migration reporting. 


## Business Context
Data warehouse migrations are a common real-world challenge for many organizations. Organizations move from legacy SQL Server environment to PostgresSQL for various reasons, including reducing licensing costs and improve flexibility. This project migrates AdventureWorksDW2025 - Microsoft's data warehouse sample database with fact and dimension tables modelling a manufacturing and sales business - from SQL Server to PostgresSQL using a production-style ETL pipeline.  


## Design Decisions

| Design                                                             | Rationale                                                                           |
|--------------------------------------------------------------------|-------------------------------------------------------------------------------------|
| Pre-migration checks catch data issues before any data migrations  | Catching defects at source is more cost effective than fixing corrupted target data |
| Post-migration row counts and referential integrity validation     | Verifies zero data loss before pipeline is considered complete (quality control)    |
| Bulk insert (100x faster) eliminates row-by-row waste              | Performance improvement - eliminate unnecessary processing overhead                 |


## Architecture

## Tech Stack

|Tool          | Purpose                  |
|--------------|--------------------------|
| Docker       | Run SQL Server on macOS  |
| Python       | Pipeline orchestration   |
| SQL Server   | Source database          |
| PostgreSQL   | Target database          |

## How to Run

## Source Database: AdventureWorksDW2025

AdventureWorksDW2025 is Microsoft's official data warehouse sample database, modelling a fictional manufacturing and sales company (AdventureWorks Cycles). It follows a classic star schema pattern used in real enterprise data warehouses. 

Database can be downloaded [here](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver17&tabs=ssms).
