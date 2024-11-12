# LITA-Sales-Data
My First Project with the Ladies in Tech Africa and the Incubator Hub.

### Project Title : Sales Data Analysis
---
[Project Overview](#project-overview)

[Data Source](#data-source)

[Tools Used](#tools-used)

[Data Cleaning and Preparations](#data-cleanind-and-preparation)

[Exploratory Data Analysis](#explanatory-data-analysis)

[Data Analysis](#data-analysis)

[SQL Query Codes](#sql-query-codes)

[Data Validation](#data-validation)


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
1. Ms Excel
Through the use of Pivot Tables and Power BI we have been able to make data validations and create dashboards which makes the Analysis done to be much more presentable and understandable by telling a story.
Below are the various Pivot Tables created drom the Sales Data;

![LITA Capstone Project Mm - Excel 09_11_2024 01_39_52~3](https://github.com/user-attachments/assets/c91983e1-42d1-403e-9663-67acce4b232b)

![LITA Capstone Project Mm - Excel 09_11_2024 01_39_52~4](https://github.com/user-attachments/assets/86217d1f-2912-4931-a809-321b6051fe28)
![LITA Capstone Project Mm - Excel 09_11_2024 01_40_04~3](https://github.com/user-attachments/assets/d0ba19b2-0815-4595-9a26-d0511a0c80cc)
![LITA Capstone Project Mm - Excel 09_11_2024 01_40_04~4](https://github.com/user-attachments/assets/d50e72e2-bac1-4819-a353-86db890b4f9c)
![LITA Capstone Project Mm - Excel 09_11_2024 01_40_04~5](https://github.com/user-attachments/assets/cd741fd3-d4ff-4ac8-a29d-022170797fee)
![LITA Capstone Project Mm - Excel 09_11_2024 01_40_04~6](https://github.com/user-attachments/assets/260fde7f-c753-4d7b-9c3a-4d030abc9887)
![LITA Capstone Project Mm - Excel 09_11_2024 01_40_13~3](https://github.com/user-attachments/assets/14e37c22-8add-4f49-81c7-ecf480834b4a)
![LITA Capstone Project Mm - Excel 09_11_2024 01_40_13~4](https://github.com/user-attachments/assets/4fcb7f04-e5ce-41de-91af-7c80365587f6)
![LITA Capstone Project Mm - Excel 09_11_2024 01_40_29~3](https://github.com/user-attachments/assets/ac0fb2a3-95b6-43c0-a017-77fe4ff783f1)
![LITA Capstone Project Mm - Excel 09_11_2024 01_40_29~4](https://github.com/user-attachments/assets/2f7b1414-86bc-497a-b682-d0f228bc61d9)
![LITA Capstone Project Mm - Excel 09_11_2024 01_40_38~3](https://github.com/user-attachments/assets/fd99bdcb-1269-4e00-ba57-36a9c5a4d70a)
![LITA Capstone Project Mm - Excel 09_11_2024 01_40_38~4](https://github.com/user-attachments/assets/3e274b98-d07e-43ee-8018-d5cb082f322d)

2. Power BI
   Power BI is a Data Visualization Tool which allows us to visualize and share insights from data which in turn helps us to make data-driven decisions by providinhg interactive reports and dashboards which can be easily understood.
   With the use of DAX Functions to create measures we have been to draw out various insighhts from the Data and create charts to enable you understand the intrincasies of Sale Data without having any professional knowledge about iit. Some of the DAX functions used are;
```
    FORMAT(SalesData[OrderDate], "YYYY-MM")
```
this particular function was used to draw out the month and year from the order date to allows us interpret the data and also give us insight on the sales made in each month of the year.
Below is an image of how our dahboard loks like with the application of the DAX function to create measure

Also we make use of slicers to give our daahboard detailed results in a way that it eill give us the results based on a specific item.
We created slicers on Region and Products 

