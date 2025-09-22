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

This SQL project tackles the challenges of real-world data inconsistencies by:

- Standardizing date formats from multiple variations.
- Normalizing text fields such as `category`, `status`, and `payment_method`.
- Removing or correcting invalid values (e.g., `price = 0`).
- Joining and filtering datasets to produce a consolidated, clean output.
- Ensuring only valid sales and returns are considered for downstream analysis.

The final result is a fully joined and cleaned dataset ready for use in analytics dashboards or reports.

---

##  Features

- Cleans and standardizes inconsistent date formats using `STR_TO_DATE`.
- Handles nulls and zero values with `COALESCE` and `NULLIF`.
- Uses `CASE` statements to categorize messy text values.
- Implements `ROW_NUMBER()` to deduplicate product entries based on rules.
- Joins cleaned product, sales, and returns data into a unified view.
- Produces a ready-to-analyze final dataset.

---

##  Technologies Used

- **SQL (MySQL compatible)**
- `CASE`, `COALESCE`, `NULLIF`, `STR_TO_DATE`
- `ROW_NUMBER()` window function
- CTEs (Common Table Expressions)
- Joins (`INNER`, `LEFT JOIN`)

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
##  Dashboard Preview

![Dashboard Screenshot](<img width="1342" height="752" alt="Amazon Dashboard" src="https://github.com/user-attachments/assets/ab787667-15cb-4fdd-b436-ce42222e312c" />
)



