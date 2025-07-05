 # DSA-KMS-CASE
This repository contains SQL queries for analysis of KMS Case Study that demostrates my skills in Data Analysis and Database Management during my study time with DSA Incubator. Designed to extract insights from various columns of data in the KMS Case exploring product improvement, marketing strategies, and customer engagement.

## Project Topic: Kultra Mega Store Sales Analysis

## Project Overview

Client Name: Kultra Mega Stores

Role: Business Intelligence Analyst

Tool Used: Structured Query Language (SQL)

## Data Source Description

Source:Excel file containing order data from 2009 to 2012

Total Records: 8,400 rows with 19 columns of Data

With each row representing sistinct characters peculiar to it. Each field Includes;

Order ID, Order Date, Ship Mode, Region, Profit, Shipping Cost, Product Category, Product Base Margin etc.

## Objectives

This project was carried out to analyze orders from 2009 to 2012 and present key insights and findings based on case scenarios. With its customer base that includes individual consumers, small businesses (retail), and large corporate clients (wholesale) across Lagos, Nigeria, inorder to monitor the growth of the business in terms of sales, profit, product improvement, marketing strategies, and customer engagement. 

## Analytical Tasks and Solution
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

## Analysis

[Case 1](https://drive.google.com/drive/folders/16YNyBzrZp_kKI-44dbIFc2P6AiYvxZFQ?usp=drive_link)

[Case 2](https://drive.google.com/drive/folders/139Joa5ktCntJUJWMMZFVHXVjkl7tZsq6?usp=drive_link)

### SQL Queries

1. ``
   select  Top 1 Product_Category, sum (Sales) as Total_Sales
from [dbo].[Project KMS]
group by Product_Category
order by Total_Sales desc 
``

# About Me

ILUPEJU BLESSING TAIWO

B.Sc in Biological Science (Pure and Applied Zoology) | Data Enthusiast| Creative Writer

I'm detailed oriented individual with a passion to uncover hidden trends and patterns that are predominately overlooked. Proficient in Data Analysis, Visualization and Reporting.

# Contact

If you found this engaging and insightful, feel free to pull or use it for learning

Email: ilupejublessing777@gmail.com

LinkedIn: https://www.linkedin.com/inblessingtaiwoilupeju
