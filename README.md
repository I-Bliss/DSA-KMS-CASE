 # 🏤 DSA-KMS-CASE
This repository contains SQL queries for analysis of KMS Case Study that demostrates my skills in Data Analysis and Database Management during my study time with DSA Incubator. Designed to extract insights from various columns of data in the KMS Case exploring product improvement, marketing strategies, and customer engagement.

## 🏗 Project Topic: Kultra Mega Store Sales Analysis

## 💠 Project Overview

Client Name: Kultra Mega Stores

Role: Business Intelligence Analyst

Tool Used: Structured Query Language (SQL)

## 📚 Data Source Description

Source:Excel file containing order data from 2009 to 2012

Total Records: 8,400 rows with 19 columns of Data

With each row representing sistinct characters peculiar to it. Each field Includes;

Order ID, Order Date, Ship Mode, Region, Profit, Shipping Cost, Product Category, Product Base Margin etc.

## 🧮 Objectives

This project was carried out to analyze orders from 2009 to 2012 and present key insights and findings based on case scenarios. With its customer base that includes individual consumers, small businesses (retail), and large corporate clients (wholesale) across Lagos, Nigeria, inorder to monitor the growth of the business in terms of sales, profit, product improvement, marketing strategies, and customer engagement. 

## ✅️ Analytical Tasks and Solution
- Case 1
1. Which product category had the highest sales
2. What are the Top 3 and Bottom 3 regions in terms of sales
3. What were the total sales of appliances in Ontario
4. Advise the management of KMS on what to do to increase the revenue from the bottom 
10 customers 
5. KMS incurred the most shipping cost using which shipping method
  
- Case 2
6. Who are the most valuable customers, and what products or services do they typically 
purchase? 
7. Which small business customer had the highest sales? 
8. Which Corporate Customer placed the most number of orders in 2009 – 2012? 
9. Which consumer customer was the most profitable one? 
10. Which customer returned items, and what segment do they belong to? 
11. If the delivery truck is the most economical but the slowest shipping method and Express Air is the fastest but the most expensive one, do you think the company appropriately spent shipping costs based on the Order Priority? Explain your answer 

## 📊 Analysis

[Case 1](https://drive.google.com/drive/folders/16YNyBzrZp_kKI-44dbIFc2P6AiYvxZFQ?usp=drive_link)

[Case 2](https://drive.google.com/drive/folders/139Joa5ktCntJUJWMMZFVHXVjkl7tZsq6?usp=drive_link)

### 🗃 SQL Queries

 ```  SQL
   select  Top 1 Product_Category, sum (Sales) as Total_Sales
from [dbo].[Project KMS]
group by Product_Category
order by Total_Sales desc 

```
![SQL 1](https://github.com/user-attachments/assets/30372953-c13b-4752-ad6c-0763551599b0)

```  SQL
select top 3 Region, sum (Sales) as Total_Sales
from [dbo].[Project KMS]
group by Region
order by Total_Sales desc

select top 3 Region, sum (Sales) as Total_Sales
from [dbo].[Project KMS]
group by Region
order by Total_Sales asc

```
![SQL 2](https://github.com/user-attachments/assets/519a937c-e19a-4314-8cd2-bcd93d89cb67)

```  SQL
select Product_Sub_Category, sum (Sales) as Total_Sales
from [dbo].[Project KMS]
where Region = 'Ontario' and Product_Sub_Category = 'Appliances'  
group by Product_Sub_Category
order by Total_Sales

```
![SQL 3](https://github.com/user-attachments/assets/14a751b8-6c5d-4f54-8d97-f09d86b6c211)

``` SQL
select top 10 Customer_Name, sum (Sales) as Total_Sales
from [dbo].[Project KMS]
Group by Customer_Name
order by Total_Sales asc

```
![SQL 4](https://github.com/user-attachments/assets/aac3f939-251e-4977-8696-4c47aa2a5081)


```  SQL
select top 1 Ship_Mode, sum (Shipping_Cost) as Total_Cost
from [dbo].[Project KMS]
group by Ship_Mode
order by Total_Cost desc

```
![SQL 5](https://github.com/user-attachments/assets/b98d3add-1065-4cde-86cc-ce19c650d00e)


```  SQL
 select top 1 Customer_Name,Product_Category,Product_Sub_Category,sum (Sales) as Total_Spent
 from [dbo].[Project KMS]
 group by Customer_Name,Product_Category,Product_Sub_Category
 Order by Total_Spent desc

```

![SQL 6](https://github.com/user-attachments/assets/4b68d0bc-287e-4150-934b-c45113db846c)


```  SQL
 select top 1 Customer_Name, sum (Sales) as Total_sales
 from [dbo].[Project KMS]
 where Customer_Segment = 'Small Business'
 group by Customer_Name
 order by Total_sales desc

```

![SQL 7](https://github.com/user-attachments/assets/ccab40e4-251c-410c-98bc-5bf3839213b4)


```  SQL
  select top 1 C.Customer_Name,count (c.Order_ID) as Order_count
 from [dbo].[Project KMS]as C
join 
	[dbo].[Order_Status]as O
on C.Order_ID = O.Order_ID
where C.Customer_Segment = 'Corporate' and year (C.Order_Date) between 2009 and 2012
group by C.Customer_Name
order by Order_count desc

```

![SQL 8](https://github.com/user-attachments/assets/5e3e5acf-d2fb-4fe5-b422-ad04865e586c)

```  SQL
select top 1 Customer_Name, sum (Profit) as Total_Profit
from [dbo].[Project KMS]
group by Customer_Name
order by Total_Profit

```

![SQL 9](https://github.com/user-attachments/assets/3bdaa90b-7cfb-4b88-b5b8-bc9209ff5205)


```  SQL
select C.Customer_Name, C.Customer_Segment
 from [dbo].[Project KMS]as C
join 
	[dbo].[Order_Status]as O
on C.Order_ID = O.Order_ID
where (O.Status) = 'Returned'

select top 10 C.Customer_Name, C.Customer_Segment
 from [dbo].[Project KMS]as C
join 
	[dbo].[Order_Status]as O
on C.Order_ID = O.Order_ID
where (O.Status) = 'Returned'

```
![SQL 10](https://github.com/user-attachments/assets/11ba8562-4270-422d-a332-8f52007b0ed0)


```  SQL
select 
	[Order_Priority],
	[Ship_mode],count (Order_ID) as Order_Count,
	round (sum (Sales-profit),2) as Estimated_shipping_cost, avg (datediff(day,[Order_Date],[Ship_Date])) as avg_ship_days
from [dbo].[Project KMS]
group by [Order_Priority], [Ship_Mode]
order by [Order_Priority], [Ship_Mode] desc

```

![SQL 11](https://github.com/user-attachments/assets/9c1ff08e-455c-4694-9161-01483adca4ca)

## 📉📍 Business Insights
- Technology is the top selling product with revenue worth in five figures. And the most valuable Customer was Emily phan with an high purchase in Technological Products

- In terms of regions with highest and least sales;
  1. 3 regions are West, Ontario, Prarie
  2. the least 3 is Nunavut, Northwest Territories, Yukon. With The total sales of Appliances in Ontario worth seven figures.

To increase Revenue for Customers with the least Revenue 
- Target low-revenue customers: Focus on customers with low revenue, such as Jeremy Farry (85.72) and Natalie DeCherney (125.90), to increase their spending.

- Analyze customer behavior: Investigate the purchasing habits and preferences of low-revenue customers to identify opportunities to upsell or cross-sell.

- Personalized marketing: Develop targeted marketing campaigns to high-potential customers, such as those with revenue between 100-200 (e.g., Natalie DeCherney, Nicole Fjeld, Katrina Edelman).

- Upselling and cross-selling: Identify opportunities to upsell or cross-sell products or services to customers who have already demonstrated a willingness to spend, such as Chris McAfee (350.18) and Eric Murdock (343.33).

KMS spent more on Delivery truck with a total cost of over 51,000

Erin Creighton placed the most orders as a Corporate customer, a total of 10 orders with the year 2009 and 2012

Dennis Kane is the Small Business Owner having the Highest sales with a total sales of 75,967

Customers that Returned items initially was over 800 rows after the query was executed but using reduced it to top 10, they are; are Dorothy Badders in Home office Segment, Grant Carroll in Corporate Segment, Michelle  Lonsdale in Home Office and Carlos Soltero in Small Business Segment

Based on Order Priority and Ship Mode, KMS did not appropriately spend shipping cost but it's understandable if they use the most expensive Ship mode ; Express Air, when the order priority is Critical but why use it wholesomely when the Order Priority is Low

- Also, it was noticed that Regular Air and Express Air was the most used the most based on Order Priority. Hence, KMS was not economical with spending on Ship Mode at all.


# 👩‍💻  About Me

ILUPEJU BLESSING TAIWO

B.Sc in Biological Science (Pure and Applied Zoology) | Data Enthusiast| Creative Writer

I'm detailed oriented individual with a passion to uncover hidden trends and patterns that are predominately overlooked. Proficient in Data Analysis, Visualization and Reporting.


# ☎️ Contact

If you found this engaging and insightful, feel free to pull or use it for learning

Email: ilupejublessing777@gmail.com

LinkedIn: https://www.linkedin.com/inblessingtaiwoilupeju
