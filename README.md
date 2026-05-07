## 📌 Project Overview
This project demonstrates the design and implementation of a professional SQL Data Warehouse. Following industry-standard practices, I built a multi-layered **Medallion Architecture** (Bronze, Silver, Gold) to transform raw, fragmented data into a high-performance analytics engine.

### 🚀 Key Learning Outcomes
*   **Data Architecture:** Designed a blueprint for data flow and storage.
*   **ETL/ELT Pipelines:** Developed automated scripts to clean and load data.
*   **Data Modeling:** Implemented a **Star Schema** with Fact and Dimension tables.
*   **Quality Engineering:** Built a suite of SQL validation tests to ensure data integrity.

---

## 🏗️ Data Architecture
The system is divided into three distinct layers to ensure a "Single Source of Truth":

1.  **Bronze (Raw):** Direct ingestion of source CSV files without modification.
2.  **Silver (Standardized):** Data cleaning, handling nulls, and data type normalization.
3.  **Gold (Analytical):** Business-ready tables optimized for BI tools and reporting.

---

## 🛠️ Tech Stack
*   **Database:** Microsoft SQL Server (T-SQL)
*   **Scripting:** Python (for automated ETL/data ingestion)
*   **Tools:** SQL Server Management Studio (SSMS), Git
*   **Modeling:** Star Schema (Dimensional Modeling)

---

## 📊 Data Model
The Gold layer utilizes a **Star Schema** to provide fast query performance:

*   **Fact Tables:** Sales Transactions
*   **Dimension Tables:** Customers, Products, Calendars

---

## 📂 Repository Structure
```text
├── scripts/
│   ├── bronze/          # DDL and Load scripts for raw data
│   ├── silver/          # Cleaning and transformation logic
│   └── gold/            # Final Star Schema modeling
|
├── docs/                # Architecture diagrams and blueprints
└── README.md
