# Executive Briefing: Retention Framework Foundations & Anomalies

**To:** VP of Marketing, Director of Customer Support  
**From:** Data Science Lead  
**Date:** June 13, 2026  
**Subject:** Core Investigative Priorities Prior to Retention Campaign Launch

---

## 📊 Core Data-Backed Churn Hypotheses

Based on exploratory data analysis linking core operational fields with actual 60-day target windows, we have mathematically isolated 5 foundational operational risk hypotheses:

### Hypothesis 1: The Critical 90-Day Transaction Decay Window
*   **Statement:** Customers who have not ordered a physical personal-care item within the past 90 days exhibit a massive, non-linear shift towards absolute churn.
*   **Evidence:** The observed churn rate sits at an optimal **11.7%** for active buyers (0–30 days recency) but violently cascades upward to **65.3%** for clients at 90–120 days, and tops out at **87.3%** for clients with more than 120 days since their last order.

### Hypothesis 2: Digital Platform Abandonment is a Leading Indicator
*   **Statement:** App/web engagement indicators drop off heavily *before* transaction drop-offs become evident in purchase patterns.
*   **Evidence:** Customers visiting the platform within the last 5 days show a minimal **18.4%** churn rate. This metric spikes aggressively to **68.8%** churn if the app has not registered a digital footprint for 20 to 30 days.

### Hypothesis 3: High-Frequency Return Patterns Corrode Customer Lifetime Value
*   **Statement:** Extreme order return rates (>50%) signal structural product mismatch or sizing frustration, resulting in churn.
*   **Evidence:** Customers with a clean return rate record have a baseline churn rate of **47.1%**. However, customers returning more than half of their items (`return_rate_180d > 0.5`) see their churn probability jump to **75.0%**.

### Hypothesis 4: Negative Order Rating Trends Signal Intentional Brand Abandonment
*   **Statement:** Low transaction-level satisfaction ratings reflect post-purchase friction that rapidly causes account death.
*   **Evidence:** High-satisfaction buyers (4.0–5.0 average ratings) show a lower **38.8%** churn rate. In contrast, users leaving poor feedback (1.0–2.0 average ratings) climb to a **51.9%** churn rate.

### Hypothesis 5: Specific Historical Campaigns are Compounding Churn Vulnerabilities
*   **Statement:** Generic, unsegmented "New Launch" notifications are underperforming and pushing customers away.
*   **Evidence:** While baseline promotional profiles stabilize at ~45% churn, the "New Launch" campaign profile registers our highest individual baseline risk segment at **51.0%** churn.

---

## ⚠️ Core Operational Investigation Mandates

Before authorizing capital outlays for upcoming retention campaigns, the corporate team must thoroughly audit and confirm three distinct operational items:

1.  **Investigate the Product Return Bottleneck:** Since a >50% return rate triggers a near-guaranteed 75% customer churn rate, operations must determine whether these returns stem from damaged items or product-reaction complaints before marketing sends discount codes.
2.  **Overhaul the "New Launch" Campaign Strategy:** The data reveals that our "New Launch" notifications are underperforming compared to standard baselines, reaching a high of 51% churn. We must pause this creative rollout immediately to fix messaging fatigue.
3.  **Establish App Engagement Triggers:** Since an absence from the app for more than 20 days leads to a 68.8% churn rate, the CRM system must deploy automated, light touchpoints at day 10 of digital absence—well before the customer crosses into the high-risk transaction drop-off zone.
