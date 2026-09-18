# Tool Selection Scenarios

## Available Tools

- Excel
- SQL (against a database)
- Python
- A BI tool (Tableau, Power BI, or Looker)
- dbt
- A combination (specify which tools)

---

## Scenario 1: Enterprise Tier Price Increase

**Scenario:** Your CFO asks: "If we increase our enterprise tier price by 8% and lose 2% of enterprise customers as a result, what's the net revenue impact this year?" She needs an answer in 30 minutes for board prep.

**Tool recommended:** Excel

**Justification:** If the dataset is small, I would use **Excel** because it can quickly calculate the 8% price increase and 2% customer loss within a few minutes, which is appropriate for this one-time analysis.

---

## Scenario 2: Regional Churn Dashboard

**Scenario:** Your Customer Success team wants a daily dashboard showing each region's churn rate against target. The dashboard will be checked every morning by 30 people across the organization.

**Tool recommended:** BI tool (Tableau, Power BI, or Looker)

**Justification:** I would use a **BI tool** because the dashboard needs to be updated daily and checked by 30 people across the organization. A BI tool allows us to share the dashboard, refresh the data regularly, and let users interact with the results over time.

---

## Scenario 3: Customer Support Tickets

**Scenario:** You've been asked to identify which of your 14,000 customer support tickets from Q3 mention "shipping delay" and categorize each by sentiment.

**Tool recommended:** Python

**Justification:** I would use **Python** because we need to search through and categorize 14,000 customer support tickets by sentiment. Python is well suited for processing and analyzing large amounts of text data.

---

## Scenario 4: Partner Integration Transactions

**Scenario:** Your colleague hands you a CSV of 1,200 rows showing transactions from a partner integration over the last week. They want a quick view of which products were most popular and a back-of-the-envelope revenue estimate.

**Tool recommended:** Python

**Justification:** I would use **Python** because I can quickly load the CSV and analyze which products were most popular and estimate the revenue.

---

## Scenario 5: Reusable Data Transformations

**Scenario:** The data engineering team is restructuring the warehouse. They've asked you to build a reusable layer of transformations that other analysts in the company will query. The transformations need to run nightly and be tested.

**Tool recommended:** dbt

**Justification:** I would use **dbt** because the team needs a reusable layer of data transformations that can be tested and run automatically every night. It is designed to help analysts work with clean, reliable, and organized data.

---

## Scenario 6: Average Order Value Comparison

**Scenario:** Your VP Marketing wants to know whether the average order value differs meaningfully between users who arrived from email vs. paid social over the last 90 days. She wants the result with a confidence interval.

**Tool recommended:** Python

**Justification:** I would use **Python** because we need to compare the average order value between two groups and calculate a confidence interval. Python makes it easy to perform the statistical analysis and clearly report the results.

---

## Scenario 7: Printable Store Performance Summary

**Scenario:** A regional manager asks you to produce a one-page printable summary of last quarter's performance for 15 store locations: top products, total revenue, and target attainment. The format will be reused next quarter.

**Tool recommended:** SQL and a BI tool

**Justification:** I would use **SQL and a BI tool** because we may need to combine data from different tables, calculate total revenue and target attainment, and identify the top products. The BI tool can then create a one-page report that can be reused next quarter.

---

## Scenario 8: Large-Scale Funnel Analysis

**Scenario:** The product team has access to a new event-stream warehouse with about 600 million rows of click-level data per month. They need a recurring funnel analysis that updates each Monday morning.

**Tool recommended:** SQL and a BI tool

**Justification:** I would use **SQL and a BI tool** because the data is very large, with about 600 million rows per month, so SQL can efficiently query and summarize the click-level data. The BI tool can then provide a recurring funnel analysis that updates every Monday morning.

---
