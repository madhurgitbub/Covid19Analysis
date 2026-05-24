SalesAnalysis_SQL_PowerBI

📌 Project Overview

This project demonstrates an end-to-end Data Analytics workflow using SQL Server and Power BI.
The main objective is to analyze sales data, clean and transform it using SQL, and create interactive dashboards in Power BI for business insights.

The project focuses on:

Data Cleaning & Transformation using T-SQL
Data Modeling
KPI Analysis
Dashboard Creation
Business Intelligence Reporting
🛠️ Tech Stack
SQL Server (SQL Express)
T-SQL
Power BI Desktop
Data Warehouse (DW) Data
Lightweight (LT) Data
📂 Project Setup
1️⃣ Install Required Tools

Make sure the following software is installed:

SQL Server Express
SQL Server Management Studio (SSMS)
Power BI Desktop
2️⃣ Restore Database

Download and restore:

Data Warehouse (DW) Data
Lightweight (LT) Data

The project mainly uses DW Data because it is more structured and suitable for analytical reporting.

3️⃣ Update Data Warehouse

Run the provided SQL scripts to:

Update tables
Clean inconsistent records
Prepare data for reporting
📊 Business Requirement & User Stories

The project is based on a business request where stakeholders need:

Sales performance tracking
Customer insights
Product analysis
Budget comparison
Regional sales overview

User stories help define:

What the business wants
Which KPIs are important
What reports are required
🧹 Data Cleaning using T-SQL

Data preparation was performed using SQL concepts such as:

Column Renaming
Combining Columns
SQL Comments
Formatting SQL Statements
WHERE Clause
ORDER BY
LEFT JOIN
CASE() Function
ISNULL() Function
🏗️ Data Modeling
FACT Tables

Contain measurable business data such as:

Sales Amount
Quantity
Budget
Dimension Tables

Contain descriptive information such as:

Customer Details
Product Information
Date Data
Region Data
📤 Data Export & Transformation

Relevant tables and columns were selected based on business requirements.

The transformed data was exported for Power BI reporting.

📈 Power BI Dashboard Development
Steps Performed
✅ Load Data

Imported cleaned SQL data into Power BI.

✅ Organize Tables

Structured tables properly for analysis.

✅ Create Relationships

Connected Fact and Dimension tables to create a proper Data Model.

✅ Import Fact_Budget

Integrated budget data for comparison analysis.

✅ Create Measures

Created DAX measures for:

Total Sales
Profit
Budget Comparison
Growth Percentage
📉 Dashboard Visualizations

The dashboard includes:

Pie Charts
Line Charts
Bar Charts
Map Visualizations
Top 10 Products Graph
KPI Cards
Sales Trend Analysis
🎯 Key Insights

The dashboard helps businesses:

Track sales performance
Identify top-selling products
Analyze customer behavior
Compare actual sales vs budget
Monitor regional growth
🚀 Learning Outcomes

Through this project, you will learn:

SQL Data Cleaning
Data Warehousing Concepts
Fact vs Dimension Tables
Power BI Data Modeling
DAX Calculations
Dashboard Design
Business Intelligence Reporting
📌 Conclusion

This project is a complete beginner-to-intermediate level Data Analytics project that demonstrates how SQL and Power BI work together to generate actionable business insights from raw sales data.
