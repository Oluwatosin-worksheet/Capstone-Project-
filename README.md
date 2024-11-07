# Sales Analysis

[Project Overview](#project-overview) 
[Data sources](#data-sources)
[Tools used](#tools-used)
[Data Cleaning](#data-cleaning) 
[Exploratory Data Analysis](#exploratory-data-analysis)
[Pivot Summarization](#pivot-summarization) 
[Sql Queries](#sql-queries)
[Data Visualization](#data-visualization) 


### Project Overview 
This data Analysis project aims to provcide insights into the sales performance of a retail store. By analysing and to explore sales data to uncover key insights such as top-selling products, regional performance, and monthly sales trends.

### Data sources

Sales Data: The primary dataset used for this analysis is the "Lita Capstone Dataset" file, containing detailed information about the each sales made by the retail store.

### Tools used

- Excel- Data cleaning [Download here](https://microsoft.com)
- Sql server- Data Analysis
- Power BI- Creating report

### Data Cleaning

In the initial data preparation phase, i performed the following tasks;
1. Data loading and inspection
2. Handling missing values
3. Data cleaning and  formatting 

### Exploratory Data Analysis 

EDA Involved exploring the sales data to answer key questions, susch as; 

- what is the overall sales trend?
- which region has top sales?
- what is the average revenue generated?

### Pivot Summarization 
Below are the summarization of the pivot tables created in Excel 
- Total sales by product
- Total sales by region
- Total sales by Month
- Average sales per product
- Total revenue per Month

<img width="754" alt="excel screenshot" src="https://github.com/user-attachments/assets/dea40db1-1a3d-4ac5-a1c2-478da6844063">


  ### Sql Queries
  Here are the SQL queries that I used to extract insights from the sales data.
  
  1 Total sales for each product category
  
  ```sql
select product, sum(revenue) AS Total_sales from  `my capstone 1 csv`
group by product;
```
2 Total sales per region

```sql
select Region, count(quantity) as region_sales from `my capstone 1 csv`
group by region;
```

3 Highest selling product

```sql
SELECT product, SUM(quantity * unitprice) AS total_sales_value
FROM `my capstone 1 csv`
GROUP BY product
ORDER BY total_sales_value desc
limit 1;
```
4 Total revenue by product 

```sql 
select product, sum(revenue) as Total_revenue from `my capstone 1 csv`
group by product;
```
5     Total monthly sales 

```sql
SELECT orderDate, SUM(revenue) AS monthly_sales
FROM `my capstone 1 csv`
WHERE orderdate= '2024'
GROUP BY orderdate;
```
6 Top 5 customer purchase 

```sql
Select OrderID, sum(revenue) from `my capstone 1 csv`
group by OrderID limit 5;
```
7 Percentage of total sales by Region 

```sql 
SELECT SUM(quantity * UnitPrice) as total_sales,REGION, SUM(quantity * UnitPrice) AS RS,
(SUM(quantity * UnitPrice) / 100)
FROM `my capstone 1 csv`
GROUP BY Region;
```
8 Product with no sales 

```sql
select product from  `my capstone 1 csv`
where revenue is null;
```

### Data Visualization 
Here is the dashboard visualization insights found in the excel and sql 

<img width="520" alt="visualization " src="https://github.com/user-attachments/assets/c59f72ca-b88a-47cf-ad29-461416147b47">


