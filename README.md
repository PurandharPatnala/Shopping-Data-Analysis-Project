# Shopping-Data-Analysis-Project

The "Shopping Data Analysis Project" is an in-depth analysis of a retail dataset from Kaggle titled "Shopping_Data." This project aimed to explore various dimensions of sales data to uncover meaningful insights into consumer behavior, sales trends, and product performance. The primary focus was on understanding overall sales patterns, seasonal variations, gender-based sales differences, and identifying which product categories performed best during different seasons.

Project Overview
The dataset includes transactional information from a retail shopping environment, which covers sales data across various categories, customer demographics, and sales over time. The project aimed to provide valuable insights into the shopping habits of consumers, analyze sales trends across seasons, and identify top-selling product categories based on different demographic factors such as gender.

Data Cleaning and Preprocessing with Excel
In the initial stages of the project, Excel was utilized to clean and preprocess the data. The dataset had several inconsistencies such as missing values, invalid data entries, and duplicated rows. Using Excel's advanced features, the following steps were performed:
Data Cleansing: Removed irrelevant or duplicate rows and filled missing values using appropriate methods (e.g., mean imputation for numerical fields).
Standardization: Ensured consistency in date formats, numeric fields, and product categories.
Data Transformation: Converted categorical variables into a usable format (e.g., gender as Male/Female, dates formatted consistently).
Pivot Tables: Used pivot tables to summarize the data, calculate totals, and analyze data across multiple dimensions such as product categories and customer demographics.




SQL Queries for Deep Data Analysis
After the initial cleanup, SQL was employed to conduct more detailed analyses and generate insights from the dataset. SQL was particularly useful for performing complex queries, aggregating data, and filtering based on specific conditions. Some of the key SQL operations included:
Total Sales for the Year: Calculated the total sales for the entire year by aggregating the "Sales" field using a SUM function and grouping by the year.
sql
Copy code
SELECT SUM(Sales) AS TotalSales
FROM ShoppingData
WHERE YEAR(SaleDate) = 2023;

Sales by Season: Analyzed sales across different seasons (e.g., Spring, Summer, Fall, Winter) by using CASE statements to categorize sales by the month and then aggregating sales by season.
sql
Copy code
SELECT CASE 
          WHEN MONTH(SaleDate) IN (12, 1, 2) THEN 'Winter'
          WHEN MONTH(SaleDate) IN (3, 4, 5) THEN 'Spring'
          WHEN MONTH(SaleDate) IN (6, 7, 8) THEN 'Summer'
          ELSE 'Fall' END AS Season,
       SUM(Sales) AS TotalSeasonSales
FROM ShoppingData
GROUP BY Season;

Sales by Gender: Explored how sales differed based on gender. This was achieved by grouping sales by the Gender field and calculating the total sales for each gender.
sql
Copy code
SELECT Gender, SUM(Sales) AS TotalSalesByGender
FROM ShoppingData
GROUP BY Gender;

Top-Selling Categories by Season: Identified which product categories generated the highest sales in each season using GROUP BY to segment sales by category and season.
sql
Copy code
SELECT Category, CASE 
                   WHEN MONTH(SaleDate) IN (12, 1, 2) THEN 'Winter'
                   WHEN MONTH(SaleDate) IN (3, 4, 5) THEN 'Spring'
                   WHEN MONTH(SaleDate) IN (6, 7, 8) THEN 'Summer'
                   ELSE 'Fall' END AS Season,
       SUM(Sales) AS TotalCategorySales
FROM ShoppingData
GROUP BY Category, Season
ORDER BY TotalCategorySales DESC;

Data Visualization with Power BI
Once the data was processed and the key metrics were calculated using SQL, I used Power BI to create interactive dashboards and visualizations. Power BI helped in presenting the analysis results in an intuitive and easily digestible format. The visualizations focused on:
Total Sales for the Year: A simple bar chart displaying total sales for each year, which provided an overview of sales trends over time.
Sales by Season: A pie chart and line graph showing sales distribution across different seasons (Winter, Spring, Summer, Fall), making it easy to identify seasonal peaks in sales.
Sales by Gender: A bar chart comparing sales performance between male and female customers, helping to understand gender-based purchasing behavior.
Top Categories by Season: A column chart showing the best-performing product categories per season, which identified key categories that performed well in specific months.
Customer Demographics: A set of slicers and filters allowing users to interact with the data by region, gender, and category to explore sales patterns further.
These visualizations were designed to help business stakeholders make data-driven decisions regarding inventory management, seasonal promotions, and targeted marketing campaigns.


Key Insights and Outcomes
Using SQL, Excel, and Power BI, I was able to uncover several valuable insights from the data, including:
Total Sales for the Year: The project revealed the overall sales for the year and demonstrated the company's performance in different months and seasons.
Sales by Season: The analysis showed distinct seasonal trends, with sales peaking during certain months (e.g., Winter holidays) and dipping during others (e.g., early Spring).
Gender-Based Sales Trends: Sales were higher for a specific gender, indicating the need for tailored marketing strategies for different demographics.
Top Categories: The project also highlighted which product categories generated the most revenue during each season, which could help optimize inventory planning and seasonal campaigns.
Sales Trends by Category: By evaluating categories such as electronics, clothing, and accessories, the analysis identified top-performing product categories and areas for potential growth.


Skills Utilized
Excel: Used for data cleaning, preprocessing, and generating initial insights through pivot tables and advanced functions.
SQL: Wrote complex queries for data aggregation, filtering, and grouping to analyze sales by year, season, and gender.
Power BI: Created interactive dashboards and visualizations to showcase key sales trends and allow stakeholders to interact with the data dynamically.

Conclusion
This project demonstrates my ability to work with large datasets, clean and preprocess the data, perform in-depth analysis using SQL, and effectively present insights through interactive Power BI dashboards. By focusing on key metrics like total sales, sales by season, gender-based purchasing trends, and identifying top-selling product categories, I was able to derive actionable business insights that could guide decision-making processes related to sales strategy, marketing, and inventory management.

