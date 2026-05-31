# TechShop BI Dashboard — Drill-down & Breakdown Analysis

## Project Overview
TechShop is a fictional global electronics e-commerce company.
This project was built as part of a Business Intelligence analyst role simulation,
where the goal is to analyze campaign, order, and sales data using Looker Studio.

## Dataset

Three data sources were used in this project:

| Table | Description | Granularity |
|---|---|---|
| techshop_campaigns | Campaign performance data (impressions, clicks, cost, turnover) | Campaign + Day |
| techshop_orders | Order-level data (customer, channel, margin) | Order |
| techshop_sales | Product-level sales data (category, quantity, unit price) | Order + Product |

## Table Relationships

- techshop_campaigns connects to techshop_orders via campaign_key
- techshop_orders connects to techshop_sales via order_id

## Key Concepts Applied

**Dimensions vs Metrics**
- Dimension: Fields used for grouping. Answers "by what?" (e.g. category_1, channel_grouping)
- Metric: Numerical fields that can be aggregated. Answers "how much?" (e.g. turnover, cost)

**Breakdown**
Splits a table by a selected dimension so all groups appear at once.
Used to compare campaign performance across channels side by side.

**Drill-down**
Allows users to click through a hierarchy from general to detailed.
Used to explore product categories and campaign channels interactively.

## Dashboard Features

### 1. Breakdown Table — Campaign Performance by Channel
- Data source: techshop_campaigns
- Dimension: campaign_name
- Breakdown Dimension: channel_grouping
- Metrics: turnover, cost, nb_transaction, ROAS
- Calculated Field: ROAS = SUM(turnover) / SUM(cost)

Key Findings:
- CRM channel has significantly higher ROAS (Flash Sale: 185, January Newsletter: 81) due to near-zero cost
- Paid Social and Paid Search have moderate ROAS (~10-13)
- YouTube Pre-Roll generates the highest turnover

### 2. Drill-down Bar Chart — Product Sales Hierarchy
- Data source: techshop_sales
- Hierarchy: category_1 → category_2 → product_name
- Metric: turnover

Key Findings:
- Accessories is the top category by turnover
- Within Accessories, Headphones and Cases are the leading sub-categories

### 3. Drill-down Bar Chart — Campaign Channel Hierarchy
- Data source: techshop_campaigns
- Hierarchy: channel_grouping → channel → campaign_name
- Metric: turnover

Key Findings:
- Paid Social is the highest turnover channel grouping
- Within Paid Social, Instagram significantly outperforms Facebook

## Live Dashboard
View on Looker Studio: (https://datastudio.google.com/u/0/reporting/dc1b8cac-488f-4db7-a2e2-7560e188cfac/page/1fqzF)

## Tools Used
- Google Sheets
- Looker Studio (Google Data Studio)

## Author
Bahadır Köksal — Data Analysis Student @ Workintech
