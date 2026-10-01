# Olist Brazilian E-Commerce Analysis

## Overview

An end-to-end analysis of the **Olist Brazilian E-Commerce Public Dataset** to understand sales performance, customer demand, product categories, delivery performance, payment behavior, and customer satisfaction.

The project demonstrates a complete data analytics workflow using **SQL, Python, Excel, and Tableau**.

## Dataset

The analysis uses the **Brazilian E-Commerce Public Dataset by Olist**, a public dataset containing approximately 100,000 orders from 2016–2018 across multiple linked datasets, including orders, customers, products, sellers, payments, and reviews.

**Source:** [Olist Brazilian E-Commerce Public Dataset — Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

The dataset is provided by Olist and is licensed under **CC BY-NC-SA 4.0**.

## Business Questions

* How did order volume and revenue change over time?
* Which product categories generated the most revenue?
* Which Brazilian states had the highest order volume?
* How long did customers typically wait for their orders?
* How did freight costs relate to product prices?
* Which payment methods and installment options were most common?
* How did delivery performance relate to customer review scores?
* Which sellers and product categories contributed most to marketplace revenue?

## Tools & Technologies

* **SQL:** DuckDB
* **Python:** Pandas, NumPy, Matplotlib, Seaborn
* **Excel:** PivotTables, XLOOKUP, formulas, dashboards
* **Tableau:** Data visualization and dashboard development
* **Dataset:** Olist Brazilian E-Commerce Public Dataset

## Analysis

### SQL & Python — Jupyter Notebook

SQL and Python analysis were conducted in a **Jupyter Notebook**.

SQL was used to analyze the relational datasets and investigate:

* Order volume and order status
* Monthly orders and revenue
* Revenue by product category
* Average order value
* Freight costs and freight-to-price ratios
* Payment methods and installment behavior
* Delivery times and delivery performance
* Customer states
* Seller performance
* Product sales and revenue
* Customer review scores

Python was then used for exploratory data analysis and visualization, including:

* Monthly order and revenue trends
* Delivery-time distribution
* Customer review score distribution
* Top product categories by revenue
* Geographic distribution of orders
* Relationship between product price and freight cost

### Excel

Excel was used to demonstrate spreadsheet-based analysis and dashboard development.

The workbook includes:

* PivotTables
* XLOOKUP-based data integration
* KPI calculations
* Monthly order analysis
* Revenue by product category
* Orders by customer state
* Average delivery time by state
* Interactive dashboard visualizations

**[View the Excel Analysis Workbook](https://drive.google.com/drive/folders/1VMzOooyiTDiOEMDCeK1ZRzNyAjjOdsoA?usp=sharing)**

### Tableau

Tableau was used to create a dashboard covering:

* Monthly order trends
* Revenue by product category
* Orders by customer state
* Average delivery performance
* Key business metrics

## Key Findings

* Order volume and revenue varied considerably over time, indicating changes in marketplace activity.
* Revenue was concentrated among a smaller number of product categories.
* Customer demand was geographically concentrated in several Brazilian states.
* Freight represented a meaningful additional cost relative to product prices and varied across products and categories.
* Credit card payments were the dominant payment method, with installment payments also widely used.
* Delivery performance varied across customer states.
* Customer review scores differed across delivery-performance groups, suggesting a relationship between delivery experience and customer satisfaction.
* A relatively small group of sellers contributed substantially to marketplace sales and revenue.

## Project Structure

```text
Olist-Brazilian-E-Commerce-Analysis/
│
├── Olist_Analysis.ipynb
├── README.md
│
└── tableau/
    └── README.md
```

The Excel workbook is hosted externally through Google Drive because of its file size.

## Outcome

This project demonstrates an end-to-end data analytics workflow, from querying relational data with SQL and performing exploratory analysis in Python to building spreadsheet and BI dashboards for communicating business insights.
