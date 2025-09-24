# Sales-Insights-Project-Power-BI-SQL-
Overview: This project uses Power BI and SQL to analyze sales data, helping the company gain insights into sales trends, identify top-performing products, and target high-value customers. The goal is to make informed business decisions that could drive an estimated revenue increase of 7% in the next quarter.
Power BI Badge SQL Badge

Overview:
This project uses Power BI and SQL to analyze sales data, helping the company gain insights into sales trends, identify top-performing products, and target high-value customers. The goal is to make informed business decisions that could drive an estimated revenue increase of 7% in the next quarter.

Power BI Dashboard
A Power BI dashboard was created to visualize key metrics like:

Total Revenue
Sales Quantity by Markets
Revenue Trends Over Time
Top Customers and Products
Table of Contents
Project Phases
Technologies Used
Key Highlights
SQL Analysis
Power BI Analysis
Conclusion
Project Phases
Requirement Gathering - Identifying business needs and relevant sales metrics.
Data Collection - Extracting sales data from company databases.
Data Processing - Cleaning and structuring data for analysis.
Data Modeling - Building models to facilitate Power BI visualizations.
Dashboard Building - Designing an interactive dashboard.
Deployment - Publishing the dashboard for stakeholders.
Technologies Used
SQL: For data extraction, transformation, and analysis.
Power BI: For creating interactive and insightful data visualizations.
Key Highlights
Developed a Power BI dashboard that provides insights into sales trends and patterns.
Enabled stakeholders to track performance and make data-driven decisions.
Identified actionable insights that can potentially increase revenue by 7%.
SQL Analysis
Here are some key SQL queries used in the analysis:

Show all customer records

SELECT * FROM customers;
Show total number of customers

SELECT COUNT(*) FROM customers;
Retrieve transactions for the Chennai market

SELECT * FROM transactions WHERE market_code = 'Mark001';
Show total revenue in the year 2020

SELECT SUM(transactions.sales_amount) 
FROM transactions 
INNER JOIN date ON transactions.order_date = date.date 
WHERE date.year = 2020 
  AND (transactions.currency = 'INR' OR transactions.currency = 'USD');
Power BI Analysis
Currency Normalization Formula
To handle multiple currencies, the norm_amount column was created in Power BI to standardize revenue using the formula below:

= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] = "USD#(cr)" then [sales_amount] * 75 else [sales_amount], type any)
This formula assumes an exchange rate of 1 USD = 75 INR.

Conclusion
This project demonstrates the value of data analysis and visualization in making informed business decisions. By analyzing sales data, the dashboard provides insights that could help increase revenue by approximately 7% next quarter. Future improvements could include:

Real-time data integration for up-to-date insights.
Predictive analytics for forecasting future sales trends.



