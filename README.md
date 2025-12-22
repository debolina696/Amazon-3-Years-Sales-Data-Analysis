# 📊 Amazon 3-Year Sales Analysis Dashboard (Power BI)

## 📌 Project Overview

This project focuses on analyzing **Amazon’s sales performance over a 3-year period** using Power BI.  
The objective is to provide a **high-level executive dashboard** that answers critical business questions related to **sales, profit, cost, targets, achievement, and growth trends** across **time, region, and category**.

The dashboard is designed for:
- Senior management
- Business analysts
- Sales & operations teams

It enables **data-driven decision-making** through interactive KPIs, dynamic metrics, and advanced time intelligence.

---

## 🎯 Business Questions (KPIs Covered – Page 1)

This dashboard answers the following **key business questions**:

1. What is the **Total Sales** generated over the last 3 years?
2. How many **Total Units** were sold?
3. What is the **Total Profit** and **Profit Margin**?
4. What is the **Total Cost** incurred?
5. What is the **Total Target** and how much has been achieved?
6. What is the **Achievement %** against targets?
7. How is the business performing **Year-over-Year (YoY %)**?
8. How do KPIs change dynamically across **MTD / QTD / YTD** periods?

---

## 🧩 KPI Metrics Implemented (Metric Toggle)

A **dynamic metric selector** is implemented to analyze multiple KPIs using a single visual:

- Total Sales  
- Total Profit  
- Total Cost  
- Profit Margin  
- Total Units Sold  
- Total Target  
- Achievement %  
- YoY %

➡ This avoids visual clutter and improves user interactivity.

---

## 🗂 Data Preparation & Transformation

### 🔹 Data Cleaning (Power Query)
- Removed duplicates and null values
- Corrected data types (Date, Numeric, Percentage)
- Standardized column names
- Cleaned category and region fields

### 🔹 Append & Merge
- **Append Queries** used to combine multi-year sales data
- **Merge Queries** used to link sales data with:
  - Product details
  - Region information
  - Target tables

---

## 🧱 Data Modeling & Relationships

- Implemented a **Star Schema**
- Fact Table:
  - Sales Transactions
- Dimension Tables:
  - Date
  - Product
  - Region
  - Category
- Separate **Target Tables** for performance comparison

✔ One-to-many relationships  
✔ Single-direction filtering  
✔ Dedicated Date table marked as Date table  

This ensures accurate aggregation and optimized performance.

---

## 📈 Dashboard Page 1 – Visual Analysis

### 1️⃣ KPI Cards
Displays:
- Total Sales
- Total Units Sold
- Total Profit
- Profit Margin
- Total Cost
- Achievement %

**Purpose:**  
Provides an instant snapshot of overall business performance.

---

### 2️⃣ Target vs Achievement Analysis
- Compares Actual Sales vs Target
- Calculates Achievement %

**Why used:**  
Helps track performance efficiency and goal completion.

**DAX Level:** Intermediate to Advanced  
- Uses `CALCULATE`, `DIVIDE`, filter context from target tables

---

### 3️⃣ Dynamic Metric Toggle (Advanced)
Allows switching between multiple KPIs in visuals.

**Why used:**  
Improves usability and enables multi-metric analysis without duplicating visuals.

**DAX Level:** Advanced  
- Disconnected table
- `SWITCH()` function
- Dynamic measure evaluation

---

### 4️⃣ 3-Year Sales & Profit Comparison
- Current Year Sales
- Last Year Sales
- YoY %
- Profit comparison

**Why used:**  
Identifies growth trends and performance changes year-over-year.

**DAX Used:**  
- `SAMEPERIODLASTYEAR()`
- `DATEADD()`
- `DIVIDE()`

---

### 5️⃣ Monthly Sales Trend (All Regions & Categories)
Line chart showing month-wise sales trend across all years.

**Purpose:**  
Identifies seasonality, demand patterns, and sales fluctuations.

---

### 6️⃣ Rolling 3-Month Average Analysis (Advanced)
Smooths short-term fluctuations to show actual sales trend.

**Why used:**  
Provides better trend visibility for management decisions.

**DAX Used:**  
- `DATESINPERIOD()`
- Rolling average logic

---

### 7️⃣ Region-wise Sales Distribution
Visualizes contribution of each region to total sales.

**Purpose:**  
Helps identify top-performing and underperforming regions.

---

### 8️⃣ Dynamic Period Analysis (MTD / QTD / YTD)
Users can dynamically switch between:
- Month-to-Date
- Quarter-to-Date
- Year-to-Date

**Why used:**  
Enables flexible time-based performance tracking.

**DAX Used:**  
- `TOTALMTD()`
- `TOTALQTD()`
- `TOTALYTD()`

---

## 🛠 Tools & Technologies Used

- Power BI Desktop
- Power Query (ETL)
- DAX (Advanced Time Intelligence)
- Star Schema Data Modeling

---

## ✅ Conclusion

This dashboard page delivers a **professional, executive-level overview** of Amazon’s sales performance by combining:
- Strong data modeling
- Advanced DAX calculations
- Target vs achievement tracking
- Dynamic and interactive KPI analysis

This page serves as the **foundation dashboard** for deeper category-wise, region-wise, and product-level analysis in subsequent pages.
- Dashboard link https://github.com/debolina696/Amazon-3-Years-Sales-Data-Analysis/blob/main/Amazon%20Sales%20Dashboard.png
