# Retail Sales Analytics Pipeline

## Project Background

As a data analyst at a large offline retail organization operating across 100+ stores, I was tasked with building an end-to-end data warehousing and BI solution to uncover insights from 10 years of sales, customer, and product data. The goal was to enable the CEO and business teams to derive strategic insights across store performance, customer loyalty, and product trends.

Insights and recommendations are provided on the following key areas:

- **Store & Regional Performance**
- **Customer Loyalty & Segmentation**
- **Product Category & Brand Trends**
- **Dashboard-Ready Reporting Layer**

The stack used includes Python for data generation and extraction, Snowflake as the data warehouse, SQL for analysis, and Power BI for visualization.

The SQL queries used to inspect and clean the data for this analysis can be found here [link].  
Targeted SQL queries regarding various business questions can be found here [link].  
An interactive Power BI dashboard used to report and explore trends can be found here [link].


## Table of Contents

- [Project Background](#project-background)
- [Data Structure & Initial Checks](#data-structure--initial-checks)
- [Executive Summary](#executive-summary)
- [Insights Deep Dive](#insights-deep-dive)
  - [Store & Regional Performance](#store--regional-performance)
  - [Customer Loyalty & Segmentation](#customer-loyalty--segmentation)
  - [Product Category & Brand Trends](#product-category--brand-trends)
  - [Dashboard-Ready Reporting Layer](#dashboard-ready-reporting-layer)
- [Recommendations](#recommendations)
- [Assumptions and Caveats](#assumptions-and-caveats)


## Data Structure & Initial Checks

The core data model follows a star schema (with elements of snowflake schema) and includes the following tables:

- **Dim_Loyalty_Info:** Customer loyalty tiers and points requirements
- **Dim_Customer:** Customer demographics and loyalty info
- **Dim_Store:** Store locations, types, and regional info
- **Dim_Product:** Product name, brand, category, and pricing
- **Dim_Date:** Daily granularity date dimension
- **Fact_Orders:** Sales transactions with quantity, discounts, shipping costs, and totals

**[Insert ERD Diagram Here]**

The data was generated using Python with Faker and pandas libraries. Approximately 1,000 customers, 1,000 products, 100 stores, and 1,000,000+ sales records were simulated, alongside 100 separate daily sales files to mimic real-time ingestion pipelines.


## Executive Summary

### Overview of Findings

Over a 10-year sales period, we discovered that:

1. **Recent stores** opened in the last year are already among the top revenue generators.
2. **Customer loyalty tiers** have a measurable impact on purchase frequency and order value.
3. **Category diversification** correlates strongly with high-value customer behavior.

These insights helped shape regional sales strategies, loyalty marketing plans, and inventory optimization efforts.

**[Insert snapshot of Power BI dashboard with key cards and visuals here]**


## Insights Deep Dive

### Store & Regional Performance

* **Top-performing stores** by revenue are those opened most recently in the past 12 months.  
* **Regional trends** show the South region consistently outperforms others in sales volume.  
* **Order density** is significantly higher in urban store formats (MBO, Exclusive).  
* **Sales variability** across stores decreases after their first 6 months of operation.

**[Insert pie chart or line graph of store type vs revenue, store opening vs revenue]**

### Customer Loyalty & Segmentation

* **Platinum-tier members** represent only 5% of customers but contribute over 25% of revenue.  
* **Customers in higher loyalty tiers** tend to have larger order sizes and more frequent purchases.  
* **Age segmentation** shows most high-value orders come from the 25-44 age range.  
* **Over 1,000 customers** were profiled, with synthetic demographics and purchase behavior generated.

**[Insert funnel chart and donut chart of loyalty tiers and age group breakdown]**

### Product Category & Brand Trends

* **Top 3 brands** generated over $200K in revenue over the past year.  
* **Most-purchased products** came from Electronics and Apparel categories.  
* **Product categories** with the most diversity attracted more repeat customers.  
* **Price sensitivity** varied across brands—premium brands sold fewer units but higher AOV.

**[Insert tree map or bar chart by product category and brand]**

### Dashboard-Ready Reporting Layer

* 25+ SQL queries were developed for ad hoc insights including:
  - Customers inactive in the past 30 days
  - Sales trends by month and year
  - Manager-wise revenue contributions
  - Cross-category purchasing behavior
* The model supports querying from both Snowflake tables and stage-layer files.

**[Insert example SQL query result screenshot]**


## Recommendations

Based on the insights and findings above, I recommend the business intelligence team consider the following:

* **Expand recently launched stores**, especially those performing well in less than 12 months.  
* **Refine loyalty program criteria** to move more customers from Gold to Platinum tiers.  
* **Introduce cross-category bundles** targeting customers who’ve engaged with >3 categories.  
* **Reallocate marketing budget** toward regions and store types showing higher conversion rates.  
* **Create manager performance dashboards** to optimize training and incentives.


## Assumptions and Caveats

* Loyalty tier logic and point thresholds were synthetically defined, not derived from actual business rules.  
* All customer, product, and transaction data were generated using Python and Faker; no PII was used.  
* Store opening dates were randomized within a 10-year window and post-cleaned via SQL.  
* Sales data was generated assuming linear distribution; real-world seasonal effects were not modeled.  
* Power BI dashboard is a prototype; UI/UX improvements can be made in future versions.
