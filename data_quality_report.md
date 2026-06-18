# Data Quality Report

Snapshot date: 2025-09-30

## customers.csv
- Rows: 2400
- Total null values: 1787
- Exact duplicate rows: 0
- Date parse issues in `signup_date`: 0

## orders.csv
- Rows: 10009
- Total null values: 80
- Exact duplicate rows: 0
- Order _DUP-looking ids: 12
- Date parse issues in `order_date`: 0
- Outliers in `gross_amount`: 536

## support_tickets.csv
- Rows: 1921
- Total null values: 0
- Exact duplicate rows: 0
- Date parse issues in `ticket_date`: 0

## web_events_snapshot.csv
- Rows: 2400
- Total null values: 0
- Exact duplicate rows: 0
- Date parse issues in `snapshot_date`: 0

## churn_labels.csv
- Rows: 2400
- Total null values: 0
- Exact duplicate rows: 0
- Date parse issues in `snapshot_date`: 0

## intervention_history.csv
- Rows: 2400
- Total null values: 0
- Exact duplicate rows: 0
- Date parse issues in `snapshot_date`: 0

## rfm_modeling_snapshot.csv
- Rows: 2400
- Total null values: 1386
- Exact duplicate rows: 0
- Date parse issues in `snapshot_date`: 0

## Referential integrity
- orders.csv: 0 records reference customer_id not in customers.csv
- support_tickets.csv: 0 records reference customer_id not in customers.csv
- web_events_snapshot.csv: 0 records reference customer_id not in customers.csv
- churn_labels.csv: 0 records reference customer_id not in customers.csv
- intervention_history.csv: 0 records reference customer_id not in customers.csv
- rfm_modeling_snapshot.csv: 0 records reference customer_id not in customers.csv

## Recommendations
- Remove/handle `_DUP` orders; treat post-snapshot orders as label-only.
- Inspect gross_amount outliers and decide (cap/log/investigate).
- Impute or add 'unknown' for loyalty/skin_type nulls before modeling.
