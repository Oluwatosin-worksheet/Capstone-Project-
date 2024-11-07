# Sales Analysis

### Project Overview 
This data Analysis project aims to provcide insights into the sales performance of a retail store. By analysing and to explore sales data to uncover key insights such as top-selling products, regional performance, and monthly sales trends.

### Data sources

Sales Data: The primary dataset used for this analysis is the "Lita Capstone Dataset" file, containing detailed information about the each sales made by the retail store.

### Tools 

- Excel- Data cleaning [Download here](https://microsoft.com)
- Sql server- Data Analysis
- Power BI- Creating report

### Data Cleaning/Preparation 

In the initial data preparation phase, i performed the following tasks;
1. Data loading and inspection
2. Handling missing values
3. Data cleaning and  formatting 

### Exploratory Data Analysis 

EDA Involved exploring the sales data to answer key questions, susch as; 

- what is the overall sales trend?
- which region has top sales?
- what is the average revenue generated?

  ### Data Analysis

  ```sql 
 SELECT * FROM my_capstone.`my capstone 1 csv`;
select product, sum(revenue) AS Total_sales from  `my capstone 1 csv`
group by product;

select Region, count(quantity) as region_sales from `my capstone 1 csv`
group by region;

SELECT product, SUM(quantity * unitprice) AS total_sales_value
FROM `my capstone 1 csv`
GROUP BY product
ORDER BY total_sales_value desc
limit 1;

select product, sum(revenue) as Total_revenue from `my capstone 1 csv`
group by product;

SELECT orderDate, SUM(revenue) AS monthly_sales
FROM `my capstone 1 csv`
WHERE orderdate= '2024'
GROUP BY orderdate;

Select OrderID, sum(revenue) from `my capstone 1 csv`
group by OrderID limit 5;

SELECT SUM(quantity * UnitPrice) as total_sales,REGION, SUM(quantity * UnitPrice) AS RS,
(SUM(quantity * UnitPrice) / 100)
FROM `my capstone 1 csv`
GROUP BY Region;

select product from  `my capstone 1 csv`
where revenue is null;
```

### Results/Findings 

