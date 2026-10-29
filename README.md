# Olist Brazilian E-Commerce Analysis

## Overview

An end-to-end analysis of the Olist Brazilian E-Commerce Public Dataset to understand sales performance, customer demand, product categories, delivery performance, payment behavior, and customer satisfaction.

The project demonstrates a complete data analytics workflow using SQL, Python, Excel, and Tableau. Its central question is whether late delivery is associated with lower customer review scores.

## Headline Finding

Of 95,824 delivered orders with a review, **6,381 (6.7%) arrived after the estimated delivery date**. These orders received an average review score of **2.27**, compared with **4.29** for orders delivered on time or early, a difference of **2.02 points** (95% CI 1.98 to 2.06; Mann-Whitney U test, p < 0.001). **62.4%** of late orders received a score of 1 or 2, compared with **9.3%** of on-time or early orders.

This is an association in observational data. Late orders may also differ by region, product category, or seller, so the analysis does not show that delay alone lowers ratings.

## Dataset

The analysis uses the Brazilian E-Commerce Public Dataset by Olist, a public dataset containing approximately 100,000 orders (99,441 order records) from 2016–2018 across multiple linked tables, including orders, customers, products, sellers, payments, and reviews. Monetary values are in Brazilian reais (BRL).

Source: [Olist Brazilian E-Commerce Public Dataset — Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

The dataset is provided by Olist and is licensed under CC BY-NC-SA 4.0.

## Business Questions

1. How did order volume and revenue change over time?
2. Which product categories generated the most revenue?
3. Which Brazilian states had the highest order volume?
4. How long did customers typically wait for their orders?
5. How did freight costs relate to product prices?
6. Which payment methods and installment options were most common?
7. How did delivery performance relate to customer review scores?
8. Which sellers and product categories contributed most to marketplace revenue?

## Tools & Technologies

- **SQL:** DuckDB
- **Python:** Pandas, NumPy, Matplotlib, Seaborn, SciPy
- **Excel:** PivotTables, XLOOKUP, formulas, dashboards
- **Tableau:** Data visualization and dashboard development
- **Dataset:** Olist Brazilian E-Commerce Public Dataset

## Methodology and Definitions

The delivery and review analysis uses the following definitions, applied consistently in both SQL and Python:

- **Delivered orders:** orders with status `delivered` and both a delivery date and an estimated delivery date recorded.
- **Late:** the order was delivered on a calendar day after the estimated delivery date. Dates are compared at day level, because estimated delivery dates are stored at midnight and a timestamp comparison would wrongly count same-day deliveries as late.
- **On time or early:** all other delivered orders.
- **One review per order:** some orders have more than one review, so the most recent review is kept for each order.
- **Exclusions:** of 99,441 orders, 96,478 were delivered, 96,470 had both delivery dates, and 95,824 had a review and were analysed (3.6% of orders excluded: 2,963 not delivered, 8 delivered without a recorded date, 646 without a review).
- **Cross-check:** the SQL (DuckDB) and Python (Pandas) calculations produce identical group sizes and average scores.

## Analysis

### SQL & Python — Jupyter Notebook

SQL and Python analysis were conducted in a Jupyter Notebook.

SQL was used to analyze the relational datasets and investigate:

- Order volume and order status
- Monthly orders and revenue
- Revenue by product category
- Average order value
- Freight costs and freight-to-price ratios
- Payment methods and installment behavior
- Delivery times and delivery performance
- Customer states
- Seller performance
- Product sales and revenue
- Customer review scores

Python was then used for data-quality checks, exploratory analysis, statistical testing, and visualization, including:

- Missing-value and duplicate checks
- Monthly order and revenue trends
- Delivery-time distribution
- Customer review score distribution
- Top product categories by revenue
- Geographic distribution of orders
- Relationship between product price and freight cost
- Review scores by delivery status, with a confidence interval for the difference in means, a Mann-Whitney U test, and a Spearman correlation between days late and review score

### Excel

Excel was used to demonstrate spreadsheet-based analysis and dashboard development.

The workbook includes:

- PivotTables
- XLOOKUP-based data integration
- KPI calculations
- Monthly order analysis
- Revenue by product category
- Orders by customer state
- Average delivery time by state
- Interactive dashboard visualizations

[View the Excel Analysis Workbook](https://docs.google.com/spreadsheets/d/1vlR8o1Wgl-eUMoxqy97hYonnXAFmkQ4v/edit?usp=drive_link&ouid=104393319960821729035&rtpof=true&sd=true)

### Tableau

Tableau was used to create a dashboard covering:

- Monthly order trends
- Revenue by product category
- Orders by customer state
- Average delivery performance
- Key business metrics

## Key Findings

- **Order volume grew strongly, then levelled off.** Monthly orders rose from 800 in January 2017 to a peak of 7,544 in November 2017, then stayed at roughly 6,000–7,300 per month through August 2018. The earliest months (late 2016) and September 2018 contain very few orders, so the dataset does not cover them fully.
- **Revenue was concentrated in a few categories.** Total product revenue was R$13.59 million. The top five categories (health and beauty, watches and gifts, bed/bath/table, sports and leisure, computer accessories) generated about 40% of it, and health and beauty led at R$1.26 million.
- **Demand was geographically concentrated.** São Paulo (SP) accounted for 41,746 orders (about 42% of the total). SP, Rio de Janeiro (RJ), and Minas Gerais (MG) together accounted for about 67%.
- **Freight was a substantial extra cost.** Total freight was R$2.25 million, about 17% of product revenue. Average freight per item was R$19.99, and the average item-level freight-to-price ratio was 32%. Furniture and large-item categories had the highest average freight.
- **Credit cards dominated payments.** Credit cards were used in 76,505 orders, compared with 19,784 for boleto, and installment payments were widely used.
- **Customers waited about 12.5 days on average** from purchase to delivery, and delivery performance varied across customer states.
- **Late delivery was strongly associated with lower reviews.** 6.7% of analysed orders arrived late; these had an average review score of 2.27 versus 4.29 for on-time or early orders (difference 2.02, 95% CI 1.98 to 2.06), and 62.4% of late orders scored 1 or 2 versus 9.3%.
- **A small group of sellers contributed a large share of sales.** The ten highest-revenue sellers, out of 3,095, accounted for about 13% of product revenue, and sellers located in SP accounted for about 64%.

## Limitations

- The data is observational, so associations (such as between late delivery and review scores) should not be read as causal effects.
- Review scores come from customers who chose to leave a review, which may not represent all customers.
- Orders without a delivery date or a review were excluded from the delivery and review analysis (3.6% of orders).
- The estimated delivery date is set by the marketplace, so "late" is measured relative to that estimate rather than to a fixed delivery standard.
- The analysis does not yet control for region, product category, or seller when comparing review scores.

## Project Structure

```
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

This project demonstrates an end-to-end data analytics workflow, from querying relational data with SQL and performing exploratory and statistical analysis in Python to building spreadsheet and BI dashboards for communicating business insights.
