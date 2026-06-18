# Part 1 — EDA Audit

This file summarizes the work in `eda_audit.ipynb`, the exploratory data analysis and data-quality audit notebook for Part 1 of the churn prediction project.

## Purpose

`eda_audit.ipynb` performs a structured audit of the raw datasets and builds a safe, pre-snapshot customer master table. It documents data quality issues, identifies invalid/unusual values, and explores churn-related patterns to support later modeling decisions.

## Key analyses in the notebook

- Load and inspect raw datasets:
  - `customers.csv`
  - `orders.csv`
  - `support_tickets.csv`
  - `web_events_snapshot.csv`
  - `churn_labels.csv`
  - `intervention_history.csv`
  - `rfm_modeling_snapshot.csv`


- Create a data quality report that includes:
  - missing values
  - duplicate rows
  - ID-level duplicate detection
  - date parsing issues
  - potential post-snapshot leakage rows
  - numeric outliers
  - referential integrity checks against `customers.csv`

- Audit invalid or unusual values for key datasets:
  - invalid age groups in `customers.csv`
  - zero or negative order values and excessive discounts in `orders.csv`
  - out-of-bounds sentiment scores and negative resolution hours in `support_tickets.csv`
  - negative activity counts in `web_events_snapshot.csv`

- Perform exploratory data analysis (EDA):
  - churn distribution
  - customer demographics and profile distributions
  - order and monetary behavior before snapshot date
  - support ticket trends and sentiment
  - return/refund behavior
  - web/app engagement measures
  - campaign/intervention history

- Build a customer-level master table with safe pre-snapshot joins:
  - merges customer demographics, churn labels, orders, support tickets, web events, and interventions
  - uses only pre-snapshot order data for feature construction
  - fills missing numeric values sensibly for model-ready output


- Compare churned vs retained customers with summary tables and charts:
  - target variable distribution
  - numeric and categorical comparisons by churn label
  - churn behavior across frequency, monetary, and engagement metrics

- Generate evidence-backed churn risk hypotheses and created a short business memo.

## Outputs produced

- `data_quality_report.md` — markdown report summarizing quality issues and recommendations.
- `business_memo.md` — short memo with churn-risk hypotheses and business recommendations.

## How to run

1. Create and activate a Python environment.
2. Install dependencies:
```bash
pip install -r requirements.txt
```
3. Open `eda_audit.ipynb` in Jupyter or VS Code.
4. Run all cells from top to bottom.

## Notes

- The notebook uses a hard snapshot date of `2025-09-30` to prevent leakage from future data.
- It builds and analyzes customer-level features using only pre-snapshot order and ticket data where appropriate.
- The notebook is designed to support Part 1 by verifying data quality and identifying the strongest churn-related signals before modeling begins.
