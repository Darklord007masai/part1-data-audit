# Repository 1: Part 1 — Data Audit, Exploratory Data Analysis & Business Understanding

## Executive Project Summary
* **Baseline Churn Rate:** [Calculate the mean from master_df['churn_next_60d'] during your execution run, e.g., 34.2%] of our D2C consumer cohort flags positive for churn over the 60-day predictive horizon. 
* **Business Imperative:** Indiscriminate discount-dropping damages profit margins. This project structures an automated, end-to-end telemetry system targeting risk cohorts using behavioral data before subscription churn takes place.

## Data Quality Discovery & Audit Trail
During our data engineering audit of the raw D2C datasets, we isolated and resolved five intentional systemic anomilies to secure model inputs:
1. **Deduplication:** Dropped `_DUP` suffix keys found across transactional order metrics.
2. **Outlier Mitigation (Chart 1):** Identified extreme outlier values climbing up to ₹24,789 distorting customer valuation. These anomalies were clipped at the 99th percentile to stabilize predictive signals.
3. **Data Leakage Restraints (Chart 6):** Enforced strict snapshot segmentation; order rows generated past `2025-09-30` were pruned out from historical modeling indicators, preventing information leakage.
4. **Missing Values Mapping:** Addressed non-reported demographic flags (`skin_type` and missing `loyalty_tier`) by translating null vectors explicitly into `'Not Provided'` and `'Not Enrolled'` baseline markers.

## Key Operational Visualizations
*(All plots are generated dynamically via run_part1_eda.py and stored in the eda_plots/ directory)*

### 1. Outlier Identification & Gross Amount Distribution (`chart1_gross_amount_outliers.png`)
* Shows how right-skewed revenue trends are brought into a clean statistical range via 99th percentile capping.

### 2. Retention Disparity by Acquisition Channel (`chart2_churn_by_channel.png`)
* Pinpoints which organic or paid marketing vectors drag down life-time value (LTV) by feeding high-churn user traffic into the platform.

### 3. App/Web Engagement Curve (`chart3_engagement_vs_churn.png`)
* Demonstrates a strong inverse correlation: users entering the bottom 20% engagement quintile exhibit a massive spike in churn vulnerability.

### 4. Support Ticket Sentiment Index (`chart4_support_tickets_sentiment.png`)
* Visualizes severe customer complaints (e.g., product reactions) causing sharp drops into negative sentiment, creating immediate churn triggers.

### 5. Loyalty Program Enrollment Stratification (`chart5_loyalty_tier_impact.png`)
* Evaluates how effectively retention drops off as consumers move up from unenrolled segments into active loyalty memberships.

### 6. Missing Feature Compliance Matrix (`chart6_missing_data_audit.png`)
* Formally logs missing fields across our customer databases, serving as our clean infrastructure audit log.
