# 📘 SQL Data Manipulation Guide

This repository provides a **hands-on SQL data manipulation and analysis guide** built around real-world examples using **PostgreSQL** and **R (via Quarto and Rmarkdown)**.  
It demonstrates how to create, clean, transform, and analyse structured data — from basic queries to performance tuning.

---

## 🚀 Overview

The project integrates:
- **PostgreSQL 17** as the database engine  
- **R + Quarto** for analysis and reporting  
- **DBI / RPostgres** packages to connect and run SQL chunks directly within `.qmd` files  

It is designed to help analysts, data scientists, and students learn how to:
- Build and populate PostgreSQL databases  
- Write efficient SQL queries  
- Profile and clean raw data  
- Analyse demographic and time-series data  
- Optimise query performance using indexing and `EXPLAIN ANALYZE`  

---

## 🧩 Repository Structure
SQL_Data_Manipulation_Guide\
│\
├── data/ # optional sample CSV or SQL datasets\
├── images/ # screenshots and figures used in the guide\
├── SQL_Data_Manipulation_Guide.qmd # main Quarto document\
├── SQL_Data_Manipulation.sql # plain-text SQL export of the PostgreSQL database\
├── README.md # project overview (this file)\
└── _quarto.yml # Quarto project configuration\



## ⚙️ Requirements

**Software:**
- [PostgreSQL 17+](https://www.postgresql.org/download/)
- [R 4.3+](https://cran.r-project.org/)
- [Quarto](https://quarto.org/)
- pgAdmin 4 (optional, for database UI)

**R Packages:**
```r
install.packages(c("DBI", "RPostgres", "dplyr", "ggplot2"))
```
🔌 Database Connection (R)

This project uses environment variables for secure connection setup.
Before rendering the Quarto file, create a .Renviron file in your project root:
```r
PGUSER=postgres
PGPASSWORD=your_password
PGHOST=localhost
PGPORT=5432
PGDATABASE=SQL_Data_Manipulation
```
Then in R / Quarto:
```r
library(DBI)
library(RPostgres)
con <- dbConnect(
  RPostgres::Postgres(),
  dbname   = Sys.getenv("PGDATABASE"),
  host     = Sys.getenv("PGHOST"),
  port     = Sys.getenv("PGPORT"),
  user     = Sys.getenv("PGUSER"),
  password = Sys.getenv("PGPASSWORD")
)
```
📊 Key Features
| Topic                       | Description                                 |
| --------------------------- | ------------------------------------------- |
| **Data Profiling**          | Completeness, min/max, and range checks     |
| **Data Transformation**     | String, numeric, and date manipulation      |
| **Aggregation & Filtering** | Summaries by month, year, decade            |
| **Derived Variables**       | Age, duration, and interval calculations    |
| **Performance Tuning**      | Indexing, query plans, and optimization     |
| **Integration**             | SQL and R visualizations combined in Quarto |

📚 **Learning Focus**

This project was developed for reproducible teaching and demonstration of:

Data cleaning workflows in SQL

Integrating SQL with R for data science

Using Quarto for automated, reproducible analytics reports


✨ Author
Habtamu Bizuayehu
📍 Perth, Western Australia
🔗 habtamuBizuayehu.com
🔗 GitHub
