# Part 1 — Data Audit, EDA & Business Understanding

D2C Customer Churn Capstone. This repo audits the raw data and explores churn drivers
before any model is built.

## How to run
1. Open `eda_audit.ipynb` in Google Colab (or Jupyter).
2. Upload the dataset CSVs (`customers.csv`, `orders.csv`, `support_tickets.csv`,
   `web_events_snapshot.csv`, `churn_labels.csv`, `intervention_history.csv`,
   `rfm_modeling_snapshot.csv`) into the runtime, or `pip install -r requirements.txt`
   and place the CSVs alongside the notebook.
3. Run all cells top to bottom.

## Key facts (snapshot = 2025-09-30)
- 2,400 customers; churn target is balanced (~47% churn in next 60 days).
- Intentional data-quality issues: `_DUP` order rows, outlier `gross_amount`,
  missing `loyalty_tier`/`skin_type`/`rating`, and post-snapshot orders that
  must NOT be used as features.

## Outputs
- `eda_audit.ipynb` — analysis notebook (6+ charts/tables)
- `data_quality_report.md` — issues found + treatment recommendations
- `business_memo.md` — what to investigate before a retention campaign
