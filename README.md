📊 Sales Data Analysis using SQL (SSMS)
🚀 Project Overview

This project focuses on performing end-to-end sales data analysis using SQL Server Management Studio (SSMS). The objective of this project is to transform raw sales data into meaningful business insights that support data-driven decision-making.

The project includes:

Database creation
Table design
CSV data import
Data cleaning
Exploratory Data Analysis (EDA)
Business insights generation using SQL queries
🎯 Objectives
Analyze overall sales performance
Identify top customers and high-performing products
Understand regional sales trends
Detect monthly and quarterly revenue patterns
Generate actionable business insights
🛠️ Tech Stack
SQL Server Management Studio (SSMS)
SQL (T-SQL)
CSV Dataset
🗄️ Database Design
Database Name
SalesProjectDB
Table Name
SalesData
📥 Data Import Process
Imported CSV dataset using Import Flat File Wizard
Verified column names and data types
Loaded data into SQL Server table
🧹 Data Cleaning

Performed:

Null value checks
Duplicate record validation
Date format conversion
Data consistency verification

Example:

SELECT *
FROM SalesData
WHERE Sales IS NULL;
📊 Exploratory Data Analysis (EDA)
Total Revenue
SELECT SUM(Sales) AS TotalRevenue
FROM SalesData;
Total Orders
SELECT COUNT(DISTINCT OrderNumber) AS TotalOrders
FROM SalesData;
Total Customers
SELECT COUNT(DISTINCT CustomerName) AS TotalCustomers
FROM SalesData;
📈 Business Analysis
🌍 Revenue by Country
SELECT 
    Country,
    SUM(Sales) AS Revenue
FROM SalesData
GROUP BY Country
ORDER BY Revenue DESC;
👥 Top Customers
SELECT TOP 5
    CustomerName,
    SUM(Sales) AS TotalSpent
FROM SalesData
GROUP BY CustomerName
ORDER BY TotalSpent DESC;
📦 Product Performance
SELECT 
    ProductLine,
    SUM(Sales) AS Revenue
FROM SalesData
GROUP BY ProductLine
ORDER BY Revenue DESC;
📅 Monthly Revenue Trend
SELECT 
    Year_ID,
    Month_ID,
    SUM(Sales) AS MonthlyRevenue
FROM SalesData
GROUP BY Year_ID, Month_ID
ORDER BY Year_ID, Month_ID;
🧠 Advanced SQL Queries
Customer Ranking using Window Function
SELECT 
    CustomerName,
    SUM(Sales) AS TotalSales,
    RANK() OVER (ORDER BY SUM(Sales) DESC) AS CustomerRank
FROM SalesData
GROUP BY CustomerName;
Running Total Revenue
SELECT 
    OrderDate,
    SUM(Sales) OVER (ORDER BY OrderDate) AS RunningRevenue
FROM SalesData;
📌 Key Insights
A small percentage of customers generated a large portion of revenue
Certain countries consistently outperformed others
Sales showed strong seasonal trends
Some product lines contributed significantly more revenue
Large deal sizes had major business impact
💡 Business Recommendations
Focus on retaining high-value customers
Increase investment in top-performing regions
Plan marketing campaigns during peak sales periods
Promote high-performing product categories
Target larger business deals for higher revenue growth
