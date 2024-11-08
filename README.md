# LITA-CAPSTONE-SALES-DATA
---

## Project Title: Sales Performance Analysis for a retail Store
---
[Project Overview](#project-overview)

[Data Source](#data-source)

[Tools Used](#tools-used)

[Data cleaning and preparation](#data-cleaning-and-preparation)

[Exploratory Data Analysis](#exploratory-data-analysis)

 [Data Analysis](#data-analysis)

 ---


### Project Overview
---
This Data aims at which enables me to tell a compelling story around this data from the iinsight gotten and to know best performance from the given Data as well as find insight within organizational Data

### Data Source
---
The primary source of Data used here is Sales Data xlsl and this is an open Data Source available for all the ladies in tech Afica to carry out their Final Examination. This is my Final Examination with Ladies in Tech Africa (Question 1)

### Tools Used
---
- Microsoft Excel [Download Here](https://www.microsoft.com)
  1. for Data Cleaning,
  2. for Analysis
  3. for Visualization
     
- SQL - Structureed Query Lanquage  
  1. Storind and processing Data in a related Database
  2. Querring of Data
  
- Github for Portfolio Building
  1. Store Share and work with others to write codes
  2. Show case work done
    
- Power BI [Download Here](https://www.microsoft.com)
  1.  Data Visualization
  2. Connect diparate Data Set
  3. find insight within given Data

### Data cleaning and preparations
---
To start with the Data cleaning, the following were carried out
  1.  Data importing and Inspection
  2.  Data cleaning and formatting
  3.  Data Validation
  4.  Removal of duplicates

### Exploratory Data Analysis
---
this aspect involves digging deep into our data to answer questiions around our data such as
  1.  Total sale for each product category
  2.  Number of sales transaction in each region
  3.  Highest selling Product by sales value
  4.  Total revenue per Product
  5.  Moonthly Sales total for the current year
  6.  Top5 Customers by total purchase amount
  7.  %total sales Contributed by each region
  8.  Products with no sales in the Last Quarter
      
### Data Analysis
---
The basic lines of codes, querries and DAX expression used during this analysis
```SQL
SELECT * From  table SalesData
GROUP By Region
```

## SQL Analysis
####   Total sale for each product category
```SQL
Select product,Sum (quantity* Unitprice) as TotalSales From [dbo].[Sales Capstone] Group by Product
```
####  Number of sales transaction in each region
![Sales by product  SD](https://github.com/user-attachments/assets/8b9b3636-7e4c-4377-b333-5b9a984a7c5c)

```SQL
Select Region, count(*) as Numberoftransactions From [dbo].[Sales Capstone] Group by Region
![SD By Region](https://github.com/user-attachments/assets/5388cef2-8fca-4b8c-b9de-3f63504ae8a7)

#### Highest selling Product by sales value
```SQL
Select Top 1 Product as HighestSellingProduct, sum(quantity* Unitprice) as SalesValue From [dbo].[Sales Capstone] Group by Product order by SalesValue desc
```
![SD Top 1](https://github.com/user-attachments/assets/a130b00b-bdfc-445c-9aa3-1be1f048c541)

####  Total revenue per Product
```SQL
Select Product, Sum(quantity* Unitprice) as Total_Revenue From [dbo].[Sales Capstone] Group by Product```
```SQL
![SD By Region](https://github.com/user-attachments/assets/163e6c1b-58a2-4b27-9d20-04e955401692)
Select Month(OrderDate) as Month, Sum(quantity* Unitprice) as MonthlySales From [dbo].[Sales Capstone]where Year(OrderDate) = Year(GETDATE())Group by Month(OrderDate) Order by Month;
```
![Sales by Month](https://github.com/user-attachments/assets/fdc3c627-da87-4640-a3a8-80267ba9b940)

```SQL
#### Top5 Customers by total purchase amount
Select Top 5 Customer_Id as Top5Customers, sum(quantity* Unitprice) as Sales From [dbo].[Sales Capstone] Group by Customer_Id order by Sales desc
```
![SD Top5 Customer](https://github.com/user-attachments/assets/430430eb-188d-46c6-ac5e-4f9c082eedf9)
###  Products with no sales in the Last Quarter
```SQL
Select Product, sum(quantity* Unitprice) as Nosales From [dbo].[Sales Capstone] Group by Product Having Sum(quantity* Unitprice) = 0
```
![No Sales](https://github.com/user-attachments/assets/ff31d8c5-81c3-49e8-89b0-120353fe19c6)



Visuals

|

