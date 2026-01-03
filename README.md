# 📊 Amazon Sales Performance Analytics Dashboard (Power BI)

##  Summary
This project presents an end-to-end **Amazon Sales Performance Analytics Dashboard** developed using **Microsoft Power BI**.  
The dashboard is designed for the enabling stakeholders to monitor revenue, product performance, customer engagement, and time-based sales trends through interactive visual analytics.

The solution converts raw e-commerce data into **actionable insights** using industry-standard KPIs such as **YTD Sales, QTD Sales, product contribution %, and trend analysis**.

---

## Business Problem Statement
Amazon generates high-volume transactional and customer data across multiple product categories.  
Decision-makers require a centralized analytical solution to answer key business questions:

- Which product categories drive the highest revenue?
- How do sales perform across months and weeks?
- Which products generate high revenue vs. high customer engagement?
- Are there seasonal or quarterly sales patterns?

This dashboard addresses these challenges by delivering a **single source of truth for sales performance analysis**.

---

## Key Performance Indicators (KPIs)
The dashboard tracks the following business-critical metrics:

- **YTD Sales ($)** – Total revenue generated in the current year  
- **QTD Sales ($)** – Revenue generated in the current quarter  
- **YTD Products Sold** – Total units sold  
- **YTD Reviews** – Customer engagement indicator  
- **% Sales Contribution by Category**  
- **Monthly & Weekly Sales Trends**

---

## Dashboard Features

### 1. Executive Sales Overview
- High-level KPI cards for quick performance assessment
- Designed for leadership and management reporting

### 2. Monthly Sales Trend Analysis
- Line chart displaying month-over-month revenue performance
- Identifies seasonality, peak sales periods, and revenue dips

### 3. Weekly Sales Distribution
- Week-level aggregation of sales values
- Enables short-term trend and volatility analysis

### 4. Category-Wise Sales Performance
- Breakdown of YTD Sales, QTD Sales, and % contribution by product category
- Supports category prioritization and inventory planning

### 5. Top Products by Revenue
- Ranking of products based on YTD Sales
- Helps identify high-performing (hero) products

### 6. Top Products by Customer Reviews
- Ranking based on total reviews
- Highlights customer engagement vs. revenue mismatch

### 7. Interactive Filters
- Product Category
- Quarter
- Enables self-service and ad-hoc analysis

---

## Data Model Overview
The dashboard follows a **star schema analytical model**.

### Fact Table
- Sales transactions (Order Date, Product ID, Price, Quantity)

### Dimension Tables
- Product (Product Name, Category)
- Date (Day, Month, Quarter, Year)

### Key Assumptions
- Sales values are pre-tax
- Review count is used as a proxy for customer engagement
- Data is aggregated for performance optimization

---

## Tools & Technologies
- **Microsoft Power BI Desktop**
- **Power Query** – Data cleaning and transformation
- **DAX** – Time intelligence and KPI calculations
- **Data Visualization Best Practices**

---

## Sample DAX Measures
```DAX
YTD Sales = TOTALYTD(SUM(Sales[SalesAmount]), 'Date'[Date])

QTD Sales = TOTALQTD(SUM(Sales[SalesAmount]), 'Date'[Date])

Category Contribution % = 
DIVIDE([YTD Sales], CALCULATE([YTD Sales], ALL(Product[Category])))
