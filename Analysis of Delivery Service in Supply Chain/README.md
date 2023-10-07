# Analysis of Delivery Service in Supply Chain

## Table of Content
* [Introduction](#introduction)
* [Entity Relationship Diagram](#entity-relationship-diagram)
* [Tools](#tools)
* [Methodology](#methodology)
* [Data Cleansing and Manipulation](#data-cleansing-and-manipulation)
* [DAX Measures](#dax-measures)
* [Insights](#insights)
* [Live Dashboard Link](https://app.powerbi.com/view?r=eyJrIjoiYmY5M2IxMzYtMDI3Yy00ODM4LWFkMWUtNmQzMjQzNzczYzI5IiwidCI6ImRmODY3OWNkLWE4MGUtNDVkOC05OWFjLWM4M2VkN2ZmOTVhMCJ9)

## Introduction
Developed an interactive report to track the delivery service level of a supply chain by analyzing key metrics against the target service level for each customer. Performed data cleaning and manipulation on over 50,000 records of data at both the order line and order level. This involved handling missing values, filtering data, changing data types, and addressing data redundancy using Power Query. Created measures using DAX to calculate the metrics. Analyzed the data and created visualizations to present the insights.

## Entity Relationship Diagram

![image](https://github.com/ritusantra/Power-BI-Projects/assets/75059347/bf70f338-0576-4666-bfeb-d111885ee042)



## Tools
* Microsoft Power BI

## Methodology
* Data cleaning and manipulation were performed in the Power Query.
* Created data model and built relationships between fact and dimension tables
* Created measures using DAX to calculate the performance metrics - OT%, I%, OTIF%, LIFR%, VOFR%, Total Quantity Ordered,
Total Orders, Total Line Orders, Total Quantity Delivered, Total Quantity Undelivered
* Visualized the data in the form of an interactive report to present the insights

## Data Cleansing and Manipulation
* Removed duplicate records from the customer table at the source CSV file
* Handled data redundancy by renaming the category of product to its correct form

### DAX Measures and Calculated Columns



## Insights

### KPI Analysis
* The actual service level across the key performance metrics are much lesser than their target metrics.

* LIFR is 65.96%. We can improve this metric by performing a product demand forecast to make sure the in-demand products are always in the warehouse and in the right quantity.

* VOFR% is 96.59% which is higher compared to other metrics. From this we can observe that even though most of the products were available in the warehouse, they were not in the right quantity and hence VOFR remained high and LIFR decreased.

* OT% and IF% is low by around 31%.
* OTIF% is low by 55.97%. More focus and strategy should be made to improve the OTIF% as it indicates an organization's efforts in fulfilling the customers orders in terms of both quantity and agreed-upon delivery dates. This metric holds significant importance, directly influencing the overall quality of the delivery service provided by the organization.

* Except the OT% all other metrics are having an upward trend when analyzed by month. This represents that consistently the organization is unable to deliver the order to customer on the agreed delivery date. The operational process involved in delivering an order that includes warehouse picking, packing and shipping services should be streamlined and aligned. For this the performance of the logistics provider could also be analyzed to understand the issue.

### Customer Analysis
* The organization has 15 distinct customers (retailers).
* Vijay Stores ordered the most number of quantities and also has the largest quantity of undelivered orders.
* Even though Vijay Stores ordered the most number of quantities Lotus Mart and Acclaimed Stores ordered most number of times compared to other customers.
* The average of delay in delivery is 0.42 days it ranges between 1-3 days. 

### Product Analysis
* There are 18 products across 3 major product category and 6 sub category.
* Most products are under the Dairy category. From this we can observe that the organization has a large contribution towards the dairy products in the market.
* The most undelivered product is Milk. 
* There is significant delay in delivery for Ghee and Butter.

### City Analysis
* The organization is operating at 3 cities across Gujarat - Ahmedabad, Vadodara, Surat.
* The largest quantity of orders are received from Vadodara and Ahmedabad.
* The trend of quantities ordered from each of the city is similar over the month. 
* Surat has highest OTIF%. Since the number of orders placed from Surat is less, the service level in terms of on time delivery and in correct quantity is higher.
