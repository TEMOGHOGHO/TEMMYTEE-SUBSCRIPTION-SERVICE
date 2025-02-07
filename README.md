##  CAPSTONE PROJECT 2: CUSTOMER SEGMENTATION FOR TEMMYTEE-SUBSCRIPTION-SERVICE

## PROJECT OVERVIEW
--- This data analysis project aims to analyse the various parameters in the data received,understand customer behavior, track subscription types, 
and identify key trends in cancellations and renewals. The goal is to tell a compelling story by building an interactive dashboard report to gather insight and make business decisions.

## DATA SOURCE: The primary source of data is LITA Capstone dataset.xlsx.

## TOOLS: 
- Microsoft Excel for data cleaning and analysis 
- Structured Query Language (SQL) for querying of data
- Power BI for Visualization
- GitHub for Portfolio building

## DATA CLEANING AND PREPARATION
At the initial stage of data cleaning and preparation, the following actions were performed;
1. Data loading and inspection
2. Handling missing variables
3. Removing duplicates
4. Data cleaning and formatting

## Exploratory Data Analysis
Some questions were answered on the data as follows;
- What are the subscription patterns?
- What is the average subscription duration?
- What are the most popular subscription types? 

# Objective:

Segment customers based on their subscription behavior, region, and purchase patterns to:
- Improve customer retention.
- Create targeted marketing strategies.
- Optimize subscription plans to boost revenue and customer retention value.

# Tools Used:
1. Excel for data cleaning and analysis.
2. SQL for querying and data manipulation.
3. Power BI for visualization and reporting.

# Expected Outcomes:
- Enhanced customer retention with personalized marketing.
- Optimized subscription offerings to drive revenue.
- Insights into the most profitable customer segments and regions.

# Tools:
- Excel
- SQL
- Power BI
- Pivot tables

# Subscription Type Report
This report provides the total number of customers for each subscription type. It highlights customer distribution across different subscription plans, offering insights into popular subscription tiers and customer preferences.

image

# Customer Subscription Analysis
Table 1: Active vs. Canceled Customers
This table presents the count of active customers compared to those who have canceled their subscriptions. This data provides an overview of customer retention and cancellation rates.

Table 2: Retention Analysis for 2022 and 2023
The second table dives deeper into customer retention trends by showing:

The number of customers who canceled their subscriptions in 2022 and 2023.
The number of customers who remained active across both years.
These insights help assess the effectiveness of retention efforts and identify patterns in customer loyalty over time.

image

Table 1: Subscription Start Date by Quarter
The first table compares the subscription start date with each quarter of the year. This analysis helps identify trends in customer sign-ups by quarter, revealing any seasonal patterns in subscription activity.

Table 2: Subscription Start Date by Type and Year
The second table provides a comparison of the subscription start date by both subscription type and year. This breakdown offers insights into how different subscription types have trended over time, helping to assess long-term customer preferences.

image

## SQL Queries for CUSTOMER SEGMENTATION FOR TEMMYTEE SUBSCRIPTION SERVICE
 "Select * from [dbo].[CustomerData]

# retrieve the total number of customers from each region.
Select region, count(CustomerID) as Total_number
 from [dbo].[CustomerData]
 group by region"
 
# the most popular subscription type by the number of customers
select subscriptionType, count(customerid) as most_Popular
from [dbo].[CustomerData]
# group by Subscription Type

# customers who canceled their subscription within 6 months
 "select customerid from [dbo].[CustomerData]
 where DATEDIFF(month,subscriptionStart,subscriptionend) <=6"

# the average subscription duration for all customers.
select avg(datediff(day,subscriptionStart,subscriptionend)) as AverageSubscriptionDuration
from [dbo].[CustomerData]

# customers with subscriptions longer than 12 months.
 select customerid, subscription_length
 from [dbo].[CustomerData]
 where DATEDIFF(month,subscriptionStart,subscriptionend) > 12

# Total revenue by subscription type
from [dbo].[CustomerData]
 
 # group by subscriptiontype;
Top 3 regions by subscription cancellations.
from [dbo].[CustomerData]
where canceled = '0'

# group by region
order by cancellation desc;
The total number of active and canceled subscriptions
sum(case when canceled= '0' then 1 else 0 end) as cancelled
from [dbo].[CustomerData];

## Visualising customer Data with Power BI

# Power BI Data Preparation
- Dataset was Imported the dataset into Power BI.
- Corrected the data types for accuracy.
- Cleaned the data by rearranging the dates to fit the date data type correctly.
