# Amazon-Sales-Analysis-using-Power-BI
The Objective of the Sales Dashboard / Business Problem
Sales management has gained importance to meet increasing competition and the need for improved methods of distribution to reduce cost and to increase profits. Sales
management today is the most important function in a commercial and business enterprise.


#The report objectives can be summarized as follows:

Calculate Total Sales: Calculate and display the total sales value for the selected period, allowing users to understand the overall revenue generated.
Calculate Profit: Calculate and visualize the total profit achieved based on the sales data, providing insights into the financial performance.
Analyze Orders: Analyze the number of orders placed during the selected period, helping to identify sales patterns and order trends.
Calculate Profit Margin: Calculate and visualize the profit margin percentage, enabling users to assess the profitability of products or services.
Compare Sales by Product with Previous Year: Compare sales performance for each product between the selected period and the previous year, highlighting growth or decline in sales.
Compare Sales by Months with Previous Year: Compare sales performance across different months between the selected period and the previous year, identifying regions with significant changes.
Display Top 5 Cities: Present a visualization showcasing the top 5 cities based on sales, allowing users to quickly identify the most lucrative locations.
Analyze Sales by Customer and Compare with Previous Year: Analyze sales data by customer, highlighting the performance of individual customers and comparing it to the previous year.
Create Slicers for Date, City, Product, and Channel: Enable users to interact with the data by providing slicers for selecting specific dates, cities, products, and channels, allowing for dynamic filtering and personalized analysis.

Steps to follow for an end-to-end Power BI Project:-

1) Gather Data
Collected the necessary data for the project. This could include data from various sources such as databases, spreadsheets, or web services. Ensure the data is accurate and relevant to your objective.

3) Power Querry – Data Extract, Transform & Load
Power Query Editor in Power BI is a powerful tool for data cleaning and transformation. We will use it Clean and transform the data to make it suitable for analysis. This may involve removing duplicates, handling missing values, merging datasets, or creating calculated columns.

5) Create a Date Table
To work with Data Analysis Expressions (DAX) time intelligence functions, there’s a prerequisite model requirement. One date table created and extracted month, month name, year, year-month.
Codes :-
     >>date = CALENDAR(MIN('Amazon Sales data'[Order_date]),MAX('Amazon Sales data'[Order_date]))
     >>Month = MONTH('date'[Date])
     >>Year = YEAR('date'[Date])
     >>Month_year = FORMAT('date'[Date],"mmm-yyyy")
     >>Month_name = FORMAT('date'[Date],"mmm")

6) Create Data Model in Power BI Desktop
Design and create a data model that represents the relationships between different tables in your data. Establish proper relationships, define keys, and establish hierarchies if needed. This step is crucial for accurate analysis and visualization

7) Develop Reports in Power BI Desktop
Use the Power BI Desktop application to create reports based on your data model. Add visualizations such as charts, tables, and maps to represent the data effectively. Apply filters, slicers, and drill-through functionalities to allow users to interact with the data.
>>took Report Background color from color_hex (website)
>>Create Slicers – Date, region, Product, and Channel
>>Create Dax measures
>>Create Visuals:
1) Sales By Product and Comparing it with last year’s Sales.
2) Sales By Month and Comparing it with last year’s Sales.
3) Sales of top 5 countries.
4) Compare Profit by channel with Previous year’s Profit
5) Sales By year and Comparing it with last year’s Sales
6) Create Cards for Sales, Profit, Profit Margin & Product Sold

6) Implementing DAX Calculations
We will use Data Analysis Expressions (DAX) to create calculated columns, measures, and calculated tables to perform complex calculations and aggregations. DAX is a powerful formula language that allows you to manipulate data within Power BI.

//Measures Total Sales
Total_sales = SUM('Amazon Sales data'[Total Revenue])

//Measures Previous Year Toal Sales
Total_Sales_LY = CALCULATE([Total_sales],SAMEPERIODLASTYEAR('date'[Date]))

//Diffrence Between Current Year Sales & Previous Year Sales
Sales vs PY = [Total_sales]-[Total_Sales_LY]

//Percentage Increase or Decrease in sales year on year (YOY%)
Sales vs PY% = DIVIDE([Sales vs PY],[Total_sales],0)

>> Total_Units = SUM('Amazon Sales data'[Units Sold])
>> Total_profit = SUM('Amazon Sales data'[Total Profit]) 
>> Profit LY = CALCULATE([Total_profit],SAMEPERIODLASTYEAR('date'[Date]))
>> Profit Vs LY = [Total_Profit]- [Profit LY]
>> Profit vs LY % = [Profit Vs LY]/[Total_Profit]
>> Profit Margin = DIVIDE([Profit],[Sales],0)
>> Total_cost = SUM('Amazon Sales data'[Total Cost])


Conclusion of Power BI Amazon Sales Dashboard Project:-

From the Year 2010 to 2017 :-
   >> Total sales, profit, cost, Average order value and units sold gradually decreased.
   >> Total sales by Month_year wise fluctuated continuously throughout the period
   >> Profit, Profit margin, units sold by channel also decreased
   >> We can observe some profit fluctuation by order priority.
