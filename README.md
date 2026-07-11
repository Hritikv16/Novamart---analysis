# Promotional Campaign Analysis

Exploratory analysis of retail promotional campaigns (Diwali and Sankranti), evaluating how different promo types affected sales volume and revenue across stores, cities, and product categories.

## Overview

The notebook (`Analysis.ipynb`) works with four datasets — campaigns, stores, products, and event-level promo data — to clean the data and measure promotion performance using two core metrics:

- **IR% (Incremental Revenue %)** — the percentage change in revenue after a promo vs. before it
- **ISU% (Incremental Sales Units %)** — the percentage change in units sold after a promo vs. before it

## Data

The notebook expects the following CSV files in the working directory:

| File | Description |
|---|---|
| `dim_campaigns.csv` | Campaign metadata (ID, name, start/end dates) |
| `fact_events.csv` | Store-level promo events: quantities and revenue before/after each promo |
| `dim_stores.csv` | Store metadata, including city |
| `dim_products.csv` | Product metadata, including category |

## What the analysis covers

1. **Data cleaning**
   - Detecting and removing duplicate event records (by store, campaign, and product)
   - Handling missing values in pre-promo quantity sold (imputed with the median)
2. **Store distribution** — number of stores per city, highlighting cities with more than 5 stores
3. **Pricing** — average base price by product category
4. **Campaign comparison** — units sold before vs. after promotion, Diwali vs. Sankranti
5. **Promo type performance** — IR% and ISU% broken down by promo type (e.g., BOGOF, discount-based)
6. **Product and store-level deep dives** — top products by incremental revenue during Sankranti; store-level performance within a selected city (Visakhapatnam) during Diwali

## Tech stack

- Python 3.10
- pandas
- matplotlib / seaborn

## Getting started

```bash
pip install pandas matplotlib seaborn jupyter
jupyter notebook Analysis.ipynb
```

Place the four CSV files listed above in the same directory as the notebook before running the cells.

## Notes

This is an exploratory analysis notebook (no markdown documentation cells inline), so this README is intended as the primary guide to what each section of the notebook does.
