# Data Dictionary for Gold Layer

## Overview

The Gold Layer is the business-level data representation, structured to support analytical and reporting use cases. It consists of **dimension tables** and **fact tables** for specific business metrics.

---

## 1. gold.dim_customers

*   **Purpose**: Stores customer details enriched with demographic and geographic data.
*   **Columns**:

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| **customer_key** | INT | Surrogate key uniquely identifying each customer record in the dimension table. |
| **customer_id** | INT | Unique numerical identifier assigned to each customer. |
| **customer_number** | NVARCHAR(50) | Alphanumeric identifier representing the customer, used for tracking and referencing. |
| **first_name** | NVARCHAR(50) | The customer's first name, as recorded in the system. |
| **last_name** | NVARCHAR(50) | The customer's last name or family name. |
| **country** | NVARCHAR(50) | The country where the customer is located. |
| **marital_status** | NVARCHAR(20) | The marital status of the customer (e.g., Single, Married). |
| **gender** | NVARCHAR(10) | The gender of the customer. |
| **birthdate** | DATE | The customer's date of birth. |
| **create_date** | DATETIME | Timestamp of when the record was originally created. |

---

## 2. gold.dim_products

*   **Purpose**: Contains descriptive attributes of the products sold, organized by category and sub-category.
*   **Columns**:

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| **product_key** | INT | Surrogate key uniquely identifying each product record. |
| **product_id** | INT | Unique numerical identifier for the product from the source system. |
| **product_number** | NVARCHAR(50) | Unique alphanumeric code for the product. |
| **product_name** | NVARCHAR(100) | Full name of the product. |
| **category** | NVARCHAR(50) | The broad classification of the product. |
| **sub_category** | NVARCHAR(50) | The specific sub-classification of the product. |
| **maintenance** | NVARCHAR(20) | Indicates if the product requires maintenance. |
| **cost** | DECIMAL(18,2) | The manufacturing or acquisition cost of the product. |

---

## 3. gold.fact_sales

*   **Purpose**: Central table containing quantitative sales measures and foreign keys linking to dimensions.
*   **Columns**:

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| **order_number** | NVARCHAR(50) | Unique identifier for each sales order. |
| **product_key** | INT | Foreign key linking to `gold.dim_products`. |
| **customer_key** | INT | Foreign key linking to `gold.dim_customers`. |
| **order_date** | DATE | The date the order was placed. |
| **shipping_date** | DATE | The date the product was shipped. |
| **due_date** | DATE | The date the payment or delivery was due. |
| **sales_amount** | DECIMAL(18,2) | Total revenue generated from the sale. |
| **quantity** | INT | Number of units sold in the transaction. |
| **price** | DECIMAL(18,2) | The unit price of the product at the time of sale. |
