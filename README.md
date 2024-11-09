# LITA-Sales-Data
My First Project with the Ladies in Tech Africa and the Incubator Hub.

### Project Title : Sales Data Analysis
---

### Project Overview
This Data Analysis project aims to analyze the Sales performance of some given products over the past 2 years. By analyzing the various parameters in the data received we seek to gather enough insight to make reasonable decisions which will enable us to tell compelling stories around the data and to provide us with the insights of the best performance of our data.

### Data Source
The primary source of Data used here is LITA CAPSTONE PROJECT which was shared as part of my project portfolio. It’s an Excel form.

### Tools Used
- Ms Excel for;
  1. Data Cleaning
  2. Analysis
  3. Visualization

- SQL Server for Querying and Analysis

- Power BI for Data Visualization and Analysis

- GitHub for Portfolio Building

### Data Cleaning and Preparations
In the First phase of the Data Cleaning and Preparation, we make use of the Microsoft Excel to perform a set of actions such as;
- Loading and Inspection of Data

- Performing Excel functions to create new data or variables/ calculate metrics

- Data Cleaning and Formatting

### Exploratory Data Analysis
This involves the exploration of data to answer some questions about the data such as;
- Top-selling products
- Regional performance
- Monthly sales trends

### Data Analysis
This is where we include some basic lines of code or queries or even some Excel Functions and even DAX expressions used during the analysis;
```
=SUM(F4*G4)
```
The above Excel Function was used to calculate the Sales of Each product sold.
![LITA Capstone Project Mm - Excel 09_11_2024 01_38_29](https://github.com/user-attachments/assets/65bb0268-3042-43c7-a21a-09f9daf11dd7)
 Then next in calculating the Total Sales By Region I made use of the SUMIF Function and for the Average Sales per Product i made use of the AVERAGEIF Function with the results of each Excel function see in the above table.
---
### SQL Query Codes
In the process of our Data Analysis we made use of the Structured Query Language SQL to extract key insights and to retrive valuable information from the Sales Data.
Below are the queries used for extracting this Key insights;
```
select SUM(Revenue)as TotalSales, Product from SalesData
group by Product
```
This Query was used in finding the Total revenue for each product sold.
```
select COUNT(OrderId)as TotalSales, Region from SalesData
group by Region
```
This Query is used to determine the number of sale transactions done in each region.
```
Select SUM (Revenue)as HighestSellingP,Product from SalesData
group by Product
order by HighestSellingP DESC
```
The above Query is for determining the highest selling product.
```
select FORMAT(OrderDate, 'yyyy-MM')as Month,
SUM(Revenue)as TotalSales from [dbo].[SalesData]
group by FORMAT(OrderDate, 'yyyy-MM')
order by Month
```
This Query gave us insights as to what the Total monthly sales are.
```
select top 5 Customer_Id,
SUM(Quantity)as TotalPurchase from SalesData
group by Customer_Id
order by TotalPurchase desc
```
The top 5 Customers by their total pusrchase amount was known through this SQL Query
```
select Region, SUM (Revenue)as TotalSales,
SUM(Revenue) * 100.0 / (select sum(Revenue) from SalesData)as PercentageOf_Sales from SalesData
group by Region
```
What the Percentage of the total sales that was contributed by each region was made known through the use of the Query above.
```
select * from SalesData
where OrderDate >= dateadd(qq, datediff(qq,0,GETDATE())-1,0)
and OrderDate < DATEADD(qq, datediff(qq,0,getdate()),0)
```
This Query help us to gain insights has to the sales made in the Last Quarter.
From the various Queries shown we have been able to gain various insights as to the performance of the sales Data and it aids our analysation better as we have been able to get key analysis from the Sales Data.


### Data Validation
Through the use of Pivot Tables and Power BI we have been able to make data validations and create dashboards which makes the Analysis done to be much more presentable and understandable by telling a story.
