# Superstore-Sales-Analysis

### Project Overview
This project analyzes Superstore sales data from 2014 to 2017 to identify trends, insights, and recommendations for business improvement. The analysis explores sales performance, customer behavior, and product trends to inform data-driven decision-making.

### Data Sources
The analysis is based on a “sample Superstore.csv dataset” containing sales data from 2014 to 2017.
[Download here](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)

### Tools Used
- Excel: Data Cleaning
- SQL Server: Data Analysis
- Power BI: Data Visualization.

### Data Cleaning/Pre-processing
Data cleaning and pre-processing were carried out at the initial stage to ensure data quality, and the following tasks were performed;
- Data loading and inspection
- Fixing the un-standardized date format
- Handling duplicates
- Data cleaning and formatting

### Exploratory Data Analysis (EDA)
The EDA process involves analyzing the Superstore sales dataset to understand the distribution of variables, identify patterns and trends, detect potential issues, and answer key questions:
1. What is the overall sales trend?
2. Who are our top 10 customers?
3. List our top 10 performing sub-categories based on profit
4. What are our sales by state and city?
5. What are our average sales by region?
6. What are our sales by segments?
7. Sales by ship mode
8. Average sales by category

### Data Analysis
Data analysis was done in SQL Server.
~~~sql
--Write a query to show the sales trend over time.
SELECT Order_Date, Ship_Date, Sales
FROM Superstore
WHERE Order_Date BETWEEN '2014-01-01' AND '2017-12-31'
AND Ship_Date BETWEEN '2014-01-01' AND '2017-12-31'
ORDER BY Order_Date, Ship_Date ASC;
~~~
~~~sql
---Who are our top 10 customers?
SELECT top 10 Customer_Name, SUM(Sales) AS TotalPurchase
FROM Superstore
GROUP BY Customer_Name
ORDER BY TotalPurchase DESC;
~~~
~~~sql
---List our top 10 performing sub-category based on profit.
SELECT top 10 Sub_Category, SUM(Profit) AS TotalProfit
FROM Superstore
GROUP BY Sub_Category
ORDER BY TotalProfit DESC;
~~~
~~~sql
---What are our sales by state and city?
SELECT State, City, SUM(Sales) AS Sales_by_location
FROM Superstore
GROUP BY State, City
ORDER BY Sales_by_location DESC;
~~~
~~~sql
---What are our average sales by regions?
SELECT Region, AVG(Sales) AS Avg_sales_by_region
FROM Superstore
GROUP BY Region
ORDER BY Avg_sales_by_region DESC;
~~~
~~~sql
---What are our sales by segments?
SELECT Segment, SUM(Sales) AS Sales_by_segment
FROM Superstore
GROUP BY Segment
ORDER BY Sales_by_segment DESC;
~~~
~~~sql
---Sales by ship_mode.
SELECT Ship_Mode, SUM(Sales) AS Sales_by_shipmode
FROM Superstore
GROUP BY Ship_Mode
ORDER BY Sales_by_shipmode DESC;
~~~
~~~sql
---Average sales by category
SELECT Category, AVG(Sales) AS Sales_by_category
FROM Superstore
GROUP BY Category
ORDER BY Sales_by_category DESC;
~~~

### Results/Findings
The analysis of Superstore sales data from 2014 to 2017 reveals:
1. Steady sales growth: Overall sales trend shows steady growth with seasonal fluctuations.
2. Key customers: The Top 10 customers contribute significantly to sales.
3. High-performing sub-categories: Copiers and Phones sub-categories drive sales and profitability.
4. Regional variations: Sales vary by region, with the South Region leading the pack.
5. Segment-specific sales: Consumer, Corporate, and Home Office segments have distinct sales patterns.
   
These findings provide insights into sales performance, customer behavior, and product trends, informing strategic decisions to drive growth and improvement.

### Recommendations
Based on the analysis, here are some recommendations:
1. Optimize Inventory Management
- Focus on high-demand product sub-categories. Ensure that high-demand product sub-categories are always in stock.
- Improve inventory forecasting: Use historical sales data to improve inventory forecasting and reduce stock-outs or overstocking.
2. Enhance Customer Relationships
- Loyalty programs: Develop loyalty programs to retain high-value customers, such as those in the top 10 customer list.
- Personalized service: Offer personalized service to key accounts to build strong relationships and increase customer satisfaction.
3. Invest in Marketing and Advertising
- Targeted marketing: Develop targeted marketing campaigns to reach specific customer segments, such as consumers or corporate customers.
- Regional marketing: Focus marketing efforts on high-growth regions, such as the South Region.
4. Optimize Logistics and Shipping
- Streamline shipping operations: Analyze shipping data to identify opportunities to reduce costs and improve efficiency.
- Consider alternative shipping options: Evaluate alternative shipping options, such as same-day delivery or in-store pickup, to improve customer satisfaction.
5. Expand Product Offerings
- Product expansion: Consider expanding product offerings in high-growth categories. 
- Product bundling: Offer product bundles or packages to increase average order value and enhance customer satisfaction.
6. Monitor and Analyze Sales Performance
- Regular sales analysis: Regularly analyze sales data to identify trends, opportunities, and challenges.
- Data-driven decision-making: Use data insights to inform business decisions and drive growth.

By implementing these recommendations, the Superstore can improve its sales performance, customer satisfaction, and overall competitiveness in the market.

### Limitations
This analysis has several limitations:

- Data scope: The analysis is based on a specific data-set (2014-2017) and may not reflect current market trends or conditions.
- External factors: The analysis does not account for external factors, such as economic changes, competitor activity, or regulatory changes, that may impact sales performance.

These limitations should be considered when interpreting the results and making strategic decisions.


  
