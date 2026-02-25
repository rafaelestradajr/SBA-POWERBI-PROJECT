# SBA-POWERBI-PROJECT
SBA FINAL
# 📊 SBA Customer & Sales Analytics — Power BI Final Project

**Author:** Rafael Estrada  
**Course:** SBA Final Project  
**Tool:** Microsoft Power BI Desktop  
**Date:** February 2026

---

## 📌 Project Overview

This project is a full end-to-end business intelligence report built in Power BI, analyzing customer behavior, sales performance, geographic distribution, and year-over-year growth trends using a real-world style e-commerce dataset.

The report transforms raw customer and order data into actionable insights through interactive dashboards, DAX measures, drill-through pages, and dynamic visualizations.

---

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `RAFAEL_ESTRADA_SBA_FINAL.pbix` | Main Power BI report file |
| `404_powerbi_SBA_dataset_Version3.csv` | Source dataset (3,035 records) |
| `README.md` | This file |

---

## 📈 Dataset Summary

| Metric | Value |
|--------|-------|
| Total Records | 3,035 |
| Unique Customers | 1,000 |
| Total Revenue | $1,304,422.50 |
| Average Order Value | $429.79 |
| Date Range | June 2022 – June 2025 |
| Payment Methods | PayPal, Credit Card, Crypto, Bank Transfer |
| Regions | Asia, Europe, North America, Other |


### Dataset Columns




- `Customer_ID` — Unique customer identifier
- `Customer_Name` — Full name
- `Email` — Customer email
- `Location` — Country
- `Registration_Date` — Date of registration/order
- `Product_ID` — Product identifier
- `Order_ID` — Unique order identifier
- `Order_Amount` — Order value in USD
- `Order_Quantity` — Units ordered
- `Payment_Method` — Payment type used
- `Registration_Year` / `Registration_Month` — Extracted date fields
- `Region` — Geographic region grouping

---

## 🛠️ Tools & Technologies

- **Microsoft Power BI Desktop** — Report building and visualization
- **DAX (Data Analysis Expressions)** — Custom measures and calculations
- **Power Query (M Language)** — Data transformation and cleaning
- **Git / GitHub** — Version control and project sharing

---

## 🔢 DAX Measures Created

```dax
-- Total Revenue
Total_Revenue = SUM('Sheet1'[Order_Amount])

-- Total Orders
Total_Orders = COUNTROWS('Sheet1')

-- Unique Customers
Unique_Customers = DISTINCTCOUNT('Sheet1'[Customer_ID])

-- Average Order Value
Average_Order_Value = AVERAGE('Sheet1'[Order_Amount])

-- Orders by Customer (for Top 10 chart)
Total_Orders_By_Customer =
VAR CurrentCustomer = SELECTEDVALUE('Sheet1'[Customer_ID])
RETURN IF(NOT ISBLANK(CurrentCustomer),
    CALCULATE(COUNTROWS('Sheet1'),
    'Sheet1'[Customer_ID] = CurrentCustomer), BLANK())

-- Customers by Location
Customers_By_Location = CALCULATE(DISTINCTCOUNT('Sheet1'[Customer_ID]))

-- Monthly Customer Count
Customers_Monthly = CALCULATE(DISTINCTCOUNT('Sheet1'[Customer_ID]))

-- Year-over-Year Comparison
Customers_Last_Year =
CALCULATE(
    DISTINCTCOUNT('Sheet1'[Customer_ID]),
    SAMEPERIODLASTYEAR('Sheet1'[Registration_Date]))

YoY_Growth =
DIVIDE([Customers_Monthly] - [Customers_Last_Year], [Customers_Last_Year])
```

---

## 📊 Report Pages & Visualizations

### Page 1 — Executive Summary
- 4 KPI Cards: Total Revenue, Total Orders, Unique Customers, Avg Order Value
- Pie Chart: Revenue by Payment Method
- Bar Chart: Revenue by Year
- Slicers: Year and Region filters
- Smart Narrative: Auto-generated text summary

### Page 2 — Sales Analysis
- Line Chart: Revenue over time (Registration_Date)
- Bar Chart: Revenue by Payment Method
- Column Chart: Monthly revenue trend by year

### Page 3 — Customer Analysis
- Table: Top customers by revenue and order count
- Bar Chart: Orders by Registration Month
- Donut Chart: Customer distribution by Region

### Page 4 — Geographic Analysis
- Map Visual: Revenue by country (bubble size = revenue)
- Bar Chart: Top 10 countries by revenue
- Table: Regional revenue summary

### Page 5 — Customer Details *(Drill-Through Page)*
- Card: Customer Name
- Table: Full order history
- Line Chart: Customer spending over time
- Pie Chart: Payment methods used by that customer
- Back Button: Returns to previous page

---

## 🔍 Key Findings

- **$1.3M total revenue** generated across 3 years (2022–2025)
- **2024 was the peak year** with $428,345 in revenue and 341 unique customers
- **PayPal leads** in revenue ($341,625 / 26.2%) but all 4 payment methods are nearly equal
- **Crypto** is used by the most customers (259 unique customers)
- **Jonathan Lewis** is the most engaged customer with 11 orders
- **Tuvalu** generates the highest revenue of any single country ($23,108)
- **61.6% of all orders** exceed $300 — indicating a premium customer profile
- Average customer places **~3 orders** over their lifetime in this dataset

---

## ⚙️ How to Open the Report

1. Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
2. Clone or download this repository
3. Open `RAFAEL_ESTRADA_SBA_FINAL.pbix` in Power BI Desktop
4. The data is embedded — no reconnection needed
5. Interact with slicers, drill-throughs, and visuals freely

---

## 📚 What I Learned

- How to connect and transform CSV data using Power Query
- How to write DAX measures including `CALCULATE`, `DISTINCTCOUNT`, `SAMEPERIODLASTYEAR`
- How to build multi-page interactive dashboards
- How to implement drill-through navigation between pages
- How to configure cross-filtering and visual interactions
- How to apply professional themes and formatting
- How to use Smart Narratives for auto-generated insights
- How to version-control a Power BI project using Git

---

## 📬 Contact


https://github.com/user-attachments/assets/263192c1-8717-4c1b-bf22-8b5d1061653c


**Rafael Estrada**  
GitHub: [@rafaelestradajr](https://github.com/rafaelestradajr)

---

*This project was completed as part of an SBA analytics course assignment using Microsoft Power BI.*
