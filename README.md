Oracle SQL E-Commerce Analysis Project:
Overview:
This repository contains a comprehensive Oracle SQL solution for an e-commerce data analysis project. It includes table creation scripts, sample data insertion, and a variety of analysis queries to gain insights into customer purchasing behavior, product performance, and sales trends.

Database Schema:
The project uses three main tables:

users - Stores customer information

products - Contains product details

purchases - Records all transactions with pricing and discount information

Key Features:

Complete Oracle SQL scripts for database setup

Sample data for immediate analysis

Comprehensive query examples covering:

Basic filtering and sorting

Aggregation and grouping

Join operations

Subqueries

View creation

Performance optimization with indexes

Advanced analytical queries including:

Customer cohort retention analysis

Discount effectiveness by category

Monthly sales performance

Setup Instructions:
Prerequisites:

Oracle Database (version 11g or later)

SQL*Plus or another Oracle client tool

Example Queries:
Here are some highlights of the analysis you can perform:

Basic Customer Purchase History:
SELECT u.username, pr.product_name, p.final_price
FROM purchases p
JOIN users u ON p.userid = u.userid
JOIN products pr ON p.productid = pr.productid
WHERE u.country = 'USA'
ORDER BY p.purchase_date DESC;

Monthly Sales Performance:
SELECT 
    EXTRACT(YEAR FROM purchase_date) AS year,
    EXTRACT(MONTH FROM purchase_date) AS month,
    SUM(final_price) AS total_revenue
FROM purchases
GROUP BY EXTRACT(YEAR FROM purchase_date), EXTRACT(MONTH FROM purchase_date)
ORDER BY year, month;
