# nexasat-sql-retention-project
SQL-based churn and CLV analysis using telecom data
# NexaSat SQL Project – Customer Churn & CLV Analysis

**Author:** Favour Vincent  
**Tools Used:** PostgreSQL, pgAdmin, VS Code  
**Focus Areas:** Churn analysis, Customer Lifetime Value (CLV), Segmentation, Retention Strategy  

## 📌 Project Overview

This project explores customer behavior and churn dynamics for a fictional telecom company, **NexaSat**, using SQL.

The goal was to uncover:
- Why customers churn
- Which segments offer the most long-term value
- What marketing strategies could reduce churn and drive upsell

## 🧠 Business Questions

- Which user groups are most likely to churn?
- How can we identify high-value customers?
- Are there patterns based on plan level, tenure, or tech support?
- What cross-sell or upsell strategies can we apply?

## 🛠 SQL Process

- Performed **data cleaning** and null checks
- Conducted **exploratory data analysis (EDA)** on user behavior
- Created a **Customer Lifetime Value (CLV)** score using weighted KPIs:
  - Monthly bill: 40%
  - Tenure: 30%
  - Call duration: 10%
  - Data usage: 10%
  - Premium plan status: 10%
- Segmented customers into:
  - High Value
  - Moderate Value
  - Low Value
  - Churn Risk
- Built **marketing strategies** using stored procedures and condition-based queries

## 🔍 Key Insights

✅ Basic plan users with low engagement showed highest churn risk  
✅ Senior citizens without tech support were ideal for **cross-sell**  
✅ Premium users with high tenure and usage had the highest **ARPU and CLV**  
✅ Multiple-line offers were effective for customers with partners or dependents  

## 💡 Key SQL Snippet – CLV Scoring Logic

```sql
UPDATE existing_users
SET clv_score = 
    (0.4 * monthly_bill) +
    (0.3 * tenure_months) +
    (0.1 * call_duration) +
    (0.1 * data_usage) +
    (0.1 * CASE WHEN plan_level = 'Premium' THEN 1 ELSE 0 END);
> 📄 **Full Report:**  
> [Download the full project PDF](https://docs.google.com/document/d/1nFBPex7wIfUvzGRqvpn_UGQQAeHdVWFounEoq9mpZNk/edit?usp=sharing) to view all SQL queries, segmentation logic, and retention strategies.

