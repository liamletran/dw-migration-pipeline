# Data Warehouse Migration Pipeline

ETL pipeline migrating a star schema, enterprise database from SQL Server to PostgresSQL - with pre/post validation and migration reporting. 


## Business Context

Data warehouse migrations are critical strategic initiatives aimed at optimizing operational costs and system performance. Facing the rising pressure of SQL Server licensing fees and the need for seamless integration into cloud ecosystems like AWS, organizations are increasingly adopting PostgreSQL as a high-performance, open-source alternative for reporting workloads.

This project demonstrates a comprehensive migration of the AdventureWorksDW2025 database from SQL Server to PostgreSQL using a production-grade ETL pipeline. The process ensures zero data loss and absolute data integrity through rigorous pre- and post-migration validation checks, including row-count matching and referential integrity audits.


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
