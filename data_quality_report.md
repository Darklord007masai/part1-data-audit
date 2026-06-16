# Data Quality & Integrity Audit Report

**Snapshot Reference Date:** 2025-09-30  
**Target Definition:** 60-Day Churn Window (2025-10-01 to 2025-11-29)

## 1. Missing Value Analysis & Mitigation Plan
Across the 2,400 primary customer universe rows, we audited missing fields across all data joins:

*   **`customers.csv` -> `loyalty_tier`:** 1,386 missing values.
    *   *Treatment:* Do not drop. Fill with a new explicit category string: `'Not_Enrolled'`.
*   **`customers.csv` -> `skin_type`:** 401 missing values.
    *   *Treatment:* Fill with `'Unknown'` to retain these rows as model features.
*   **`orders.csv` -> `rating`:** 80 orders are missing satisfaction scores.
    *   *Treatment:* Exclude these specific rows when calculating historical averages, or impute with individual customer median ratings if available.

## 2. Duplicate Records Analysis
*   **Identified Anomaly:** 12 intentional duplicate-like records were uncovered in `orders.csv` possessing a `_DUP` suffix in their `order_id` string (e.g., `ORD008249_DUP`).
*   *Treatment:* These must be filtered and dropped from the dataset during feature extraction to avoid artificial volume or revenue inflation.

## 3. Outlier Detection & Strategy
*   **Identified Anomaly:** `orders.csv` -> `gross_amount` distribution shows a tight 75th percentile of ₹907.43, but a maximum spike reaching up to **₹24,789.38** (specifically driven by high-ticket Fragrance and Skin Care bundle orders, such as order `ORD006374` by `CUST01868`).
*   *Treatment:* Apply an exponential clip or log-transform on currency-based fields to minimize numerical model instability.

## 4. Leakage Rule Compliance (Strict Prevention)
*   **Critical Risk:** `orders.csv` contains rows with transaction dates stretching out to `2025-11-29`. 
*   *Enforcement:* All order records with `order_date > '2025-09-30'` must be fully segmented away. They are strictly reserved for defining target variables and must never bleed into customer descriptive modeling inputs.
