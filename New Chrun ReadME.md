# SaaS Customer Churn Exploratory Data Analysis & Retention Strategy

## Executive Summary
This project evaluates transactional and demographic friction points across subscriber cohorts by deploying an end-to-end Python exploratory data analysis (EDA) pipeline auditing customer billing behaviors and contract structures. The analysis revealed that month-to-month subscribers experiencing repeat payment processing failures account for 41.8% higher churn than annual subscribers, leading to targeted contract conversion and automated billing recommendations designed to recapture an estimated $340,000 in annual recurring revenue (ARR).

---

## Business Problem Statement
Subscription-based recurring revenue relies on low churn rates to maintain scalable margins. Leadership identified an increasing churn velocity in recent quarters but lacked clarity regarding whether customer attrition stemmed from pricing elasticity, payment processing friction, or contract structure preferences.

The objectives of this project are:
1. Conduct an audit across numeric distributions, schema hygiene, and variable bounds.
2. Determine which operational and demographic drivers correlate most strongly with customer cancellation.
3. Deliver quantitative recommendations to finance, product, and retention teams to safeguard Customer Lifetime Value (LTV).

---

## Analytical Methodology & The 6-Step EDA Framework
The dataset was processed through a standardized exploratory framework:

[1. Importation & Audit]  --> [2. Hygiene & Deduplication] --> [3. Range & Stats Auditing]
|
v
[6. Strategic Translation] <-- [5. Bivariate & Segments]   <-- [4. Visual Distributions]



1. **Data Importation & Schema Auditing**: Ingested raw transactional records, mapping variables against core subscription business concepts.
2. **Data Hygiene & Cleaning**: Standardized categorical churn responses (`Yes`/`No`) into binary states (`1`/`0`), resolved column data types, and purged duplicate entries.
3. **Summary Statistics & Value Range Auditing**: Computed parametric (`mean`, `std`) and non-parametric (`median`, `IQR`) statistics while checking absolute `min` and `max` values to identify operational outliers and anomalies.
4. **Distribution Analysis**: Mapped univariate distribution profiles for continuous metrics (Monthly Fee, Total Revenue) and frequency counts for categorical attributes.
5. **Bivariate & Cohort Segmentation**: Evaluated interaction patterns between contract duration, payment failures, discount application, and churn probability.
6. **Insight Communication**: Formatted raw analytical findings into leadership-facing strategies.

---

## Tech Stack & Technical Skills Demonstrated
- **Languages & Libraries**: Python 3.10+, Pandas (Data Wrangling & Transformation), NumPy (Vectorized Range Auditing), Matplotlib & Seaborn (Visual Analytics).
- **Analytical Techniques**: Value Range Auditing, Outlier Detection, Univariate & Bivariate Correlation, Customer Cohort Segmentation, Attrition Rate Normalization.
- **Domain Focus**: SaaS Recurring Revenue, Churn Analytics, Retention Strategy, Payment Processing Fallout.

---

## Results & Quantified Business Recommendations

### Core Findings
- **Contract Length Vulnerability**: Month-to-month contracts exhibit an attrition rate exceeding 42%, while multi-year contracts maintain churn below 8%.
- **High-Tier Pricing Sensitivity**: Subscribers in the upper quartile of monthly fees (above the 75th percentile) show disproportionate churn velocity unless an initial promotional discount was applied.
- **Payment Failure Compounding**: Accounts logging $\ge 2$ payment failures have a 3.4x higher churn rate, demonstrating that technical payment friction contributes to involuntary churn.

### Quantified Action Plan
1. **Contract Upsell Program (Marketing/Sales)**: Offer a 10% annual billing discount to month-to-month users upon their 3rd renewal, targeting a 15% conversion to 1-year agreements to preserve an estimated **$180,000 in ARR**.
2. **Automated Dunning & Gateway Routing (Engineering/FinOps)**: Introduce dynamic payment retries and self-service billing update notifications to prevent involuntary drop-offs, projected to reduce processing-related churn by **22%**.
3. **High-Fee Value Audits (Customer Success)**: Target enterprise-tier subscribers with monthly charges in the upper quartile for quarterly onboarding and optimization reviews.

---

## Next Steps & Project Limitations
- **Project Limitations**: The dataset reflects historical quarterly churn records and lacks granular qualitative customer service transcripts, limiting visibility into voluntary sentiment-driven cancellations.
- **Hosting Workaround Disclosure**: Cleaned data was exported via flat `.csv` for repository hosting and demonstration purposes; production environments should run directly against live PostgreSQL/Snowflake data warehouse connections.
- **Next Steps**: Conduct an A/B test on payment failure dunning emails and build an interactive Power BI drill-down dashboard tracking retention trends by geographic cohort.