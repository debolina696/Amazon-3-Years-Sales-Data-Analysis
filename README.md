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
- yoy % 

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
- Dashboard 1  link https://github.com/debolina696/Amazon-3-Years-Sales-Data-Analysis/blob/main/Amazon%20Sales%20Dashboard.png
- ## 👥 Employee Performance Analysis – Amazon (Dashboard Page 2)

### 📌 Dashboard Objective
This dashboard focuses on evaluating **employee-wise sales performance** over a 3-year period.  
It helps business leaders understand **how individual employees perform against assigned targets**, identify **top and underperformers**, and analyze performance trends across **time periods (Month / Quarter / Year)**.

---

## 🎯 Business Questions Answered

1. What is the **total sales contribution** by each employee?
2. What is the **total target assigned** to each employee?
3. How much **target has been achieved (%)** employee-wise?
4. Who are the **top and bottom performing employees**?
5. How does employee performance vary by **Month / Quarter / Year**?
6. Which employees are **most influential** in driving higher achievement?
7. How many **employees and employee categories** are involved in sales?

---

## 📊 Key KPIs Displayed

- **Total Sales**
- **Total Employee Target**
- **Achievement %**
- **Count of Employees**
- **Count of Employee Categories**

A **dynamic period slicer** (Month / Quarter / Year) allows flexible performance analysis.

---

## 🧱 Data Model & Schema Overview

### 🔹 Fact Tables
- **Sales Fact**  
  Contains transactional sales data linked to employees and dates.

- **Employee Target Fact**  
  Stores employee-wise targets at **quarter level**.

### 🔹 Dimension Tables
- **Date Table** (Year, Quarter, Month)
- **Employee Table** (EmployeeID, EmployeeName, Category)

### 🔹 Relationships
- Date ↔ Sales (1:* )
- Employee ↔ Sales (1:* )
- Employee ↔ Employee Target (1:* )
- Date ↔ Employee Target (via QuarterStart)

✔ Star-schema based  
✔ Single-direction filters  
✔ Optimized for time intelligence and performance comparison

---

## 📈 Visual (Diagram-wise) Analysis

### 1️⃣ Employee-wise Total Sales (Bar Chart)
Shows total sales generated by each employee.

**Why used:**  
Quickly identifies **top revenue contributors**.

**DAX Type:** Basic aggregation (`SUM`)

---

### 2️⃣ Employee-wise Total Target (Bar Chart)
Displays assigned targets for each employee.

**Why used:**  
Provides clarity on **expectation vs output**.

---

### 3️⃣ Employee Target vs Achievement (Table)
Shows:
- Employee Name  
- Total Sales  
- Employee Target  
- Achievement %  
- Count of Transactions  

**Why used:**  
Central performance comparison table for managers.

**DAX Level:** Intermediate  
Uses `CALCULATE`, filter context, and ratio measures.

---

### 4️⃣ Achievement % Calculation (Advanced KPI)

**Logic:**  
Achievement % = Actual Sales ÷ Employee Target

**Why used:**  
Standard metric to measure goal completion.

**DAX Type:** Intermediate–Advanced  
Handles filter context by employee and period.

---

### 5️⃣ Dynamic Period Analysis (Month / Quarter / Year)
Users can switch time granularity dynamically.

**Why used:**  
Avoids multiple reports and enables flexible analysis.

**DAX Used:**  
- Time-intelligence with context-aware calculations

---

### 6️⃣ Key Influencers Visual
Identifies factors that increase or decrease **Achievement %**.

**Why used:**  
Helps understand **which employees and patterns drive higher performance**.

**Business Value:**  
Supports coaching, incentives, and workforce optimization.

---

## 🧮 DAX & Calculation Highlights

- Employee-wise aggregations using `CALCULATE`
- Target vs Actual comparison measures
- Dynamic context handling across:
  - Employee
  - Time (Month / Quarter / Year)
- Percentage calculations using `DIVIDE`
- Advanced filter propagation via relationships

---

## 🛠 Data Preparation (Power Query)

- Cleaned employee names and categories
- Standardized date formats
- Created QuarterStart field for target alignment
- Removed duplicates and null records
- Merged employee attributes into fact tables

---

## ✅ Summary

This dashboard provides a **professional, business-ready employee performance view** by combining:
- Employee-level target tracking
- Achievement-based KPIs
- Dynamic time analysis
- Influencer-driven insights

It enables management to make **data-driven decisions** related to performance monitoring, goal setting, and employee optimization.
-Dashboard 2 link - https://github.com/debolina696/Amazon-3-Years-Sales-Data-Analysis/blob/main/Target%20vs%20Achivement.png
## 🛒 Category & Product Performance Analysis – Amazon (Dashboard Page 3)

### 📌 Dashboard Objective
This dashboard focuses on analyzing **category-wise, subcategory-wise, and product-wise performance** over a 3-year period.  
The goal is to identify **top-performing categories and products**, analyze **sales, profit, cost, and units sold**, and support **product-level decision-making**.

It enables stakeholders to understand:
- Which categories and subcategories drive maximum revenue
- Which products are most profitable
- How cost and profit vary across products
- Overall product portfolio performance

---

## 🎯 Business Questions Answered

1. What is the **total sales by category**?
2. Which **subcategories contribute the most** to sales?
3. Which **products are top-performing** by sales?
4. What is the **total cost and profit** at product level?
5. How many **categories, subcategories, and products** exist?
6. How many **units are sold** across all products?
7. How do metrics change dynamically for **Sales / Profit / Cost / Orders**?

---

## 📊 Key KPIs Displayed

- **Category-wise Total Cost**
- **Total Units Sold**
- **Count of Categories**
- **Count of Subcategories**
- **Count of Products**

A **dynamic metric toggle** allows switching between:
- Total Sales  
- Total Profit  
- Total Cost  
- Total Orders  

---

## 🧱 Data Model & Schema (Relevant Tables)

### 🔹 Fact Table
- **Sales Fact**
  - Sales Amount
  - Cost
  - Profit
  - Units Sold
  - Product Key
  - Date Key

### 🔹 Dimension Tables
- **Product Table** (Product, Subcategory, Category)
- **Date Table** (Year, Month)

### 🔹 Relationships
- Product → Sales (1 : *)
- Date → Sales (1 : *)

✔ Star schema  
✔ Single-direction filters  
✔ Optimized for product-level analysis

---

## 📈 Visual (Diagram-wise) Analysis

### 1️⃣ Category-wise Total Sales (Pie Chart)
Displays sales contribution of each category.

**Why used:**  
Quick comparison of category dominance in overall revenue.

**DAX Type:** Basic aggregation (`SUM`)

---

### 2️⃣ Subcategory-wise Sales Analysis (Bar Chart)
Shows sales distribution across subcategories.

**Why used:**  
Identifies strong and weak subcategories within each category.

---

### 3️⃣ Product-wise Sales Performance (Bar Chart)
Ranks products based on total sales.

**Why used:**  
Helps identify **top-selling products**.

---

### 4️⃣ Product Sales, Profit & Cost Details (Table)
Displays:
- Product Name
- Category
- Subcategory
- Total Sales
- Total Profit
- Total Cost

**Why used:**  
Provides **granular product-level insights** for business users.

**DAX Level:** Intermediate  
Uses multiple measures with shared filter context.

---

### 5️⃣ Dynamic Metric Toggle (Advanced Feature)
Users can switch visuals between:
- Sales
- Profit
- Cost
- Orders

**Why used:**  
Reduces report duplication and improves interactivity.

**DAX Level:** Advanced  
- Disconnected table
- `SWITCH()` logic
- Dynamic measure evaluation

---

### 6️⃣ Units Sold KPI
Displays total units sold across all products.

**Why used:**  
Helps understand **volume-driven performance** separate from revenue.

---

## 🧮 DAX & Calculation Highlights

- Aggregations using `SUM`
- Dynamic KPI switching using `SWITCH`
- Context-aware calculations by:
  - Category
  - Subcategory
  - Product
- Reusable base measures for Sales, Profit, Cost, Units

---

## 🛠 Data Preparation (Power Query)

- Cleaned product names and categories
- Standardized category & subcategory values
- Removed duplicates
- Ensured numeric consistency for cost and sales
- Validated product-category hierarchy

---

## ✅ Summary

This dashboard delivers a **professional product and category performance view** by combining:
- Category & subcategory contribution analysis
- Product-level profitability insights
- Dynamic KPI selection
- Clean data modeling and DAX logic

It supports **inventory planning, pricing decisions, and product strategy** for business stakeholders.
- Dashboard 3 link - https://github.com/debolina696/Amazon-3-Years-Sales-Data-Analysis/blob/main/Category%20Dashboard.png
- ## 🌍 Region & City Performance Analysis – Amazon (Dashboard Page 4)

### 📌 Dashboard Objective
This dashboard provides a **geographical performance analysis** of Amazon sales over a 3-year period.  
It helps stakeholders evaluate **region-wise and city-wise sales, profit, cost, and targets**, and understand how different locations contribute to overall business performance.

The dashboard supports:
- Regional performance comparison
- City-level sales and profitability analysis
- Target vs actual evaluation by region
- Strategic geographic decision-making

---

## 🎯 Business Questions Answered

1. How many **regions and cities** are contributing to sales?
2. What is the **total sales by region and city**?
3. What is the **total profit and cost** at city level?
4. How do **regions perform against assigned targets**?
5. Which **cities are top and bottom performers**?
6. How is sales distributed geographically?
7. How do sales and profit vary **city-wise within regions**?

---

## 📊 Key KPIs Displayed

- **Count of Regions**
- **Count of Cities**
- **Region-wise Total Target**
- **Total Sales**

These KPIs provide a quick summary of **geographical scale and performance**.

---

## 🧱 Data Model & Schema (Relevant Tables)

### 🔹 Fact Tables
- **Sales Fact**
  - Sales Amount
  - Profit
  - Cost
  - City
  - Region
  - Date

- **Region Target Table**
  - Region Name
  - Target Amount

### 🔹 Dimension Tables
- **Date Table** (Year, Month)
- **Region Table**
- **City Table**

### 🔹 Relationships
- Date → Sales (1 : *)
- Region → Sales (1 : *)
- City → Sales (1 : *)
- Region → Target (1 : *)

✔ Star schema  
✔ Single-direction filters  
✔ Optimized for geographic aggregation

---

## 📈 Visual (Diagram-wise) Analysis

### 1️⃣ Region & City Performance Matrix (Table)
Displays:
- Region
- City
- Total Sales
- Total Profit
- Total Cost

**Why used:**  
Provides a **detailed comparative view** of city performance within each region.

**DAX Level:** Intermediate  
Uses context-based aggregation.

---

### 2️⃣ Total Sales & Total Profit by City (Clustered Bar Chart)
Compares sales and profit across cities.

**Why used:**  
Identifies **high-revenue but low-profit** cities and vice versa.

---

### 3️⃣ Total Sales by City (Donut Chart)
Shows percentage contribution of each city to total sales.

**Why used:**  
Quick visualization of **city-wise sales distribution**.

---

### 4️⃣ Region-wise Target KPI
Displays total target assigned across regions.

**Why used:**  
Helps management evaluate **regional performance expectations**.

---

## 🧮 DAX & Calculation Highlights

- Aggregations using `SUM`
- Region and city level context filtering
- Target comparison using `CALCULATE`
- Reusable base measures for:
  - Total Sales
  - Total Profit
  - Total Cost
  - Target

---

## 🛠 Data Preparation (Power Query)

- Standardized region and city names
- Removed duplicate city records
- Validated city–region mapping
- Ensured numeric consistency for sales, profit, and cost
- Cleaned and aligned target data by region

---

## ✅ Summary

This dashboard delivers a **clear and professional geographical performance view** by combining:
- Region-wise target analysis
- City-level sales and profit insights
- Clean data modeling
- Business-focused visual storytelling

It supports **regional planning, expansion strategy, and location-based performance optimization**.
- Dashboard 4 link https://github.com/debolina696/Amazon-3-Years-Sales-Data-Analysis/blob/main/Region%20Wise%20Dashboard.png
- Datasource kaggle Amazon Sales data "C:\Users\Debolina\OneDrive\Desktop\Git Hub\amazon_like_sales_3yr.xlsx"
