Customer Churn & Revenue Retention Analysis

An end-to-end data analysis project: Python (cleaning, EDA, modeling) → SQL (business queries) → Power BI (executive dashboard) → written stakeholder recommendation.

Business Problem


Subscription revenue has plateaued despite steady new customer acquisition. Leadership suspects churn is eating into growth but lacks clear visibility into who's churning, why, and what it's costing the business.



Brief: Identify churn drivers, quantify revenue impact, and recommend actionable retention interventions — backed by a dashboard leadership can monitor monthly.

Key Questions Answered


What's the overall and segment-level churn rate, and how is it trending?
Which customer segments (plan, tenure, usage, acquisition channel) churn most?
What's the revenue impact of churn vs. new acquisition?
What early-warning signals predict churn before it happens?
Which 2-3 interventions would have the highest ROI?


Key Findings (TL;DR)


Overall churn rate: 24.3%, with month-to-month contract customers churning at ~1.55x the odds of annual contract customers, controlling for other factors.
Customers showing both declining usage and a recent cancellation-request ticket churn at 80.2%, vs. a 24.3% baseline — a 3.3x risk multiplier now used as the core watchlist signal.
Revenue lost to churn is concentrated in specific acquisition channels, not evenly spread — meaning retention spend should be targeted, not blanket.
Full findings: writeup/eda_findings.md and writeup/model_summary.md.


Tech Stack


Python (pandas, scikit-learn, matplotlib/seaborn) — data cleaning, feature engineering, EDA, logistic regression
SQL (PostgreSQL/SQLite) — cohort retention, revenue-impact, and watchlist queries using window functions and CTEs
Power BI — 3-page executive dashboard (summary, diagnostic, action/watchlist)


A Note on the Data

This project uses a synthetic dataset (~1.6M rows across customers, transactions, usage logs, and support tickets) generated in Python rather than a public Kaggle dataset, in order to control for realistic churn patterns and realistic data messiness (missing values, inconsistent date formats, duplicates, outliers) to clean. Patterns were deliberately tuned to be correlated-but-noisy rather than deterministic, so the modeling results reflect genuine signal extraction rather than recovering an artificially clean label.

Project Structure

data/        raw and cleaned CSVs
notebooks/   Python scripts (data generation, cleaning/EDA/modeling)
sql/         SQL queries (cohort retention, revenue impact, watchlist)
dashboard/   Power BI file + supporting data
writeup/     EDA findings, model summary, one-page business recommendation

