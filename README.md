# Sales Data SQL Analysis

A SQL-based exploratory data analysis (EDA) and business intelligence project built on a sample sales dataset (`sales_data_sample`). The project walks through data exploration, cleaning, and a series of queries designed to answer core business questions about revenue, customers, regions, products, and trends.

## 📊 Project Overview

**Goal:** Use SQL to measure revenue performance, identify top customers, analyze trends, and support business decisions.

The dataset (`sales_data_sample`) contains **2,823 records** across **19 countries**, representing **307 unique orders** from **92 customers**.

## 🗂️ Table of Contents

1. [Business Understanding](#1-business-understanding)
2. [Data Exploration (EDA)](#2-data-exploration-eda)
3. [Data Cleaning](#3-data-cleaning)
4. [Core Business Metrics](#4-core-business-metrics)
5. [Trend Analysis](#5-trend-analysis)
6. [Regional Analysis](#6-regional-analysis)
7. [Customer Analysis](#7-customer-analysis)
8. [Product Analysis](#8-product-analysis)
9. [Deal Size Analysis](#9-deal-size-analysis)
10. [Business Insights](#10-business-insights)

---

## 1. Business Understanding

**Goals:**
- Measure revenue performance
- Identify top customers
- Analyze trends
- Support business decisions

## 2. Data Exploration (EDA)

- **Total Records:** Count of all rows in the dataset using `COUNT(*)`
- **Distinct Countries:** List of unique countries present in the data using `SELECT DISTINCT`

## 3. Data Cleaning

- **Remove Duplicates:** Identify duplicate `OrderNumber` entries using `GROUP BY` + `HAVING COUNT(*) > 1`
- **Fix Date Format:** Standardize the `OrderDate` column into proper `DATETIME` format using `TRY_CONVERT`

## 4. Core Business Metrics

- **Total Revenue:** Sum of all sales (`SUM(Sales)`)
- **Total Orders:** Count of distinct orders (`COUNT(DISTINCT OrderNumber)`)
- **Total Customers:** Count of distinct customers (`COUNT(DISTINCT CustomerName)`)

## 5. Trend Analysis

- **Monthly Revenue Trend:** Revenue aggregated by `Year_ID` and `Month_ID`
- **Quarterly Performance:** Revenue aggregated by `Year_ID` and `QTR_ID`

## 6. Regional Analysis

- **Revenue by Country:** Total sales grouped by country, ordered by revenue
- **Top 3 Countries:** The three highest-revenue countries (USA, Spain, France)

## 7. Customer Analysis

- **Top 5 Customers:** Highest-spending customers using `TOP 5` with `SUM(Sales)`
- **Customer Ranking:** Full customer ranking using the `RANK()` window function

## 8. Product Analysis

- **Sales by Product Line:** Revenue grouped by `ProductLine` (e.g., Classic Cars, Vintage Cars, Motorcycles)

## 9. Deal Size Analysis

- **Revenue by Deal Size:** Revenue grouped by `DealSize` (Small, Medium, Large)
- **Running Total Revenue:** Cumulative revenue over time using a window function (`SUM(Sales) OVER (ORDER BY OrderDate)`)
- **Moving Average (3 Months):** Rolling 3-period average revenue using `AVG(Sales) OVER (... ROWS BETWEEN 2 PRECEDING AND CURRENT ROW)`

## 10. Business Insights

Key takeaways from the analysis:

- 💰 Revenue is **concentrated among top customers**
- 🌍 Certain **countries dominate** sales performance
- 📈 Sales show **seasonal peaks**
- 🚗 Specific **product lines generate maximum revenue**
- 📦 **Large deals** significantly impact overall revenue

---

## 🛠️ Tech Stack

- **SQL Server** (T-SQL syntax: `TOP`, `TRY_CONVERT`, window functions)
- Sample dataset: `sales_data_sample`

## 🚀 How to Use

1. Load the `sales_data_sample` dataset into your SQL Server instance.
2. Run the queries in order (EDA → Cleaning → Metrics → Trends → Regional → Customer → Product → Deal Size).
3. Review the business insights generated from the aggregated results.

## 📌 Notes

- Queries use T-SQL syntax; minor adjustments may be needed for MySQL/PostgreSQL (e.g., replace `TOP N` with `LIMIT N`, and `TRY_CONVERT` with equivalent date-casting functions).
- Window functions (`RANK()`, `SUM() OVER`, `AVG() OVER`) require SQL Server 2012+ or an equivalent modern SQL engine.
