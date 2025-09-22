# Amazon Products Catalog Insights 

This project demonstrates end-to-end data cleaning, transformation, and analysis using **SQL** for a fictional Amazon sales dataset. The final output is a **Power BI Dashboard** that visualizes key business metrics.


---
## 💡 Project Objectives

- Clean and standardize inconsistent product, sales, and returns data
- Join multiple data sources into a single analytical dataset
- Visualize KPIs like:
  - Total Orders, Returns, Revenue
  - Orders by Region
  - Payment Method Usage
  - Top 5 Products by Sales
  - Trends Over Time
  - Order Status by Category & Region

---

##  Description

This SQL project focuses on **cleaning, organizing, and combining raw business data** to make it ready for analysis, reporting, or dashboard creation. In real-world datasets, the information is often **messy, inconsistent, or incomplete** — and this project solves those problems step by step.

Here’s what the project does in detail:

---

###  1. Standardizes Different Date Formats

In the raw data, dates are written in many different formats, such as:
- `01/02/2023`
- `2023-02-01`
- `2023/02/01`

This can cause errors during analysis.  
The SQL script **detects and converts all these formats into one consistent date format**, making it easier to sort, filter, and analyze dates accurately.

---

###  2. Cleans Up Text Fields (Like Category, Status, Payment Method)

Text fields often include:
- Typos (e.g., `inactve` instead of `inactive`)
- Extra spaces or inconsistent casing (e.g., ` Electronics ` or `PAY PAL`)
- Symbols or underscores (e.g., `home_kitchen`)

The project uses SQL functions like `LOWER()`, `TRIM()`, `REPLACE()`, and `CASE` to **standardize these text values** into clean, readable labels such as:
- `pay pal` → `PayPal`
- `home_kitchen` → `Home & Kitchen`

---

###  3. Removes or Fixes Invalid Data

The raw data includes some incorrect or missing values, such as:
- Prices equal to `0` or missing
- Sales without valid dates
- Quantities that are zero or negative

These records are **filtered out** so that only accurate and reliable data is used in the final output.

---

###  4. Removes Duplicate Products (Keeps Only the Best One)

Sometimes, the same product appears more than once in the catalog.  
This project uses the `ROW_NUMBER()` function to:
- Keep the product with the **earliest launch date**
- Prefer the record with the **highest price**
- Ensure only **one clean version** of each product remains

---

###  5. Combines Sales, Product, and Return Data into One Unified Table

Using SQL joins, the script combines data from:
- 🛍 Product catalog
-  Sales transactions
-  Return records

Each row in the final dataset includes:
- Product details (name, category, status)
- Sales info (date, quantity, price, region, payment method)
- Return info (return date and reason, if any)

---

###  6. Filters for Valid Sales and Returns Only

The script ensures data quality by:
- Including only sales with **valid dates, non-zero prices, and quantities**
- Matching only those returns that are linked to real sales and products

---

###  Final Output

The result is a **clean, complete dataset** that is:
- Free from duplicates and invalid entries
- Standardized across all key fields
- Joined from multiple sources into a single table

This makes the dataset **ready for use in dashboards, reports, or business analysis tools** like Power BI, Tableau, or Excel.


---

##  Features

- Cleans and standardizes inconsistent date formats using `STR_TO_DATE`.
- Handles nulls and zero values with `COALESCE` and `NULLIF`.
- Uses `CASE` statements to categorize messy text values.
- Implements `ROW_NUMBER()` to deduplicate product entries based on rules.
- Joins cleaned product, sales, and returns data into a unified view.
- Produces a ready-to-analyze final dataset.

---

 ## Usage

Execute the full SQL script to:
Clean and transform raw data
Join product, sales, and return records
Generate a final, clean dataset

Example final output:

SELECT * FROM final_cleaned_data;

 ##  HIGHLIGHTS OF THIS DATA CLEANING PIPELINE
-- =============================================
-  Normalizes messy category, status, region, and payment fields using CASE + LOWER/TRIM/REPLACE
-  Handles multiple date formats using COALESCE + STR_TO_DATE for robust parsing
-  Removes duplicate products using ROW_NUMBER based on launch date, price, and name
-  Filters out invalid sales (null dates, zero price/quantity) before joins
-  Standardizes return reasons into consistent categories (e.g. 'Defective', 'Late Delivery')
-  Uses LEFT JOIN to preserve all sales even if no return data exists
-  Structured with modular CTEs for clarity, reusability, and maintainability

##  Learnings

- Practical SQL data wrangling for real-world messiness
- Understanding of data pipelines for analytics
- Hands-on experience integrating SQL and Power BI
- 
##  Dashboard Preview

![Dashboard](<img width="1342" height="752" alt="Amazon Dashboard" src="https://github.com/user-attachments/assets/f675ea12-aaab-4c90-8eb0-aaf2bd8960b3" />
)


