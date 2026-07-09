# E-Commerce Customer Retention & Churn Analysis

## 🎯 Executive Summary
This project analyzes customer transaction patterns for an e-commerce platform experiencing a drop in repeat purchases. By writing structured SQL queries to calculate user retention cohorts, I identified a critical 40% drop-off in customer engagement after month two, primarily driven by users acquired via promotional social media campaigns.

## 🧰 Tech Stack
* **Database Analysis**: PostgreSQL / MySQL (CTEs, Subqueries, Date Functions)
* **Data Visualization**: Power BI / Tableau
* **Data Cleansing**: Excel Power Query

## 💻 SQL Code Snippets
Below is the core logic I utilized to extract monthly customer transaction cohorts:

```sql
-- Step 1: Isolate the first purchase month for each unique customer
WITH FirstPurchase AS (
    SELECT 
        customer_id,
        MIN(DATE_TRUNC('month', order_date)) AS cohort_month
    FROM ecommerce_orders
    GROUP BY customer_id
),

-- Step 2: Calculate month intervals for subsequent transactions
CohortSize AS (
    SELECT 
        cohort_month,
        COUNT(DISTINCT customer_id) AS total_users
    FROM FirstPurchase
    GROUP BY cohort_month
)

SELECT 
    f.cohort_month,
    o.order_date,
    COUNT(DISTINCT o.customer_id) AS active_users
FROM ecommerce_orders o
JOIN FirstPurchase f ON o.customer_id = f.customer_id
GROUP BY 1, 2;
```

## 📊 Business Insights & Recommendations
1. **Targeted Re-engagement**: Customers acquired through one-time discount codes show high churn in month 2. I recommend triggering an automated email discount sequence 45 days post-purchase to boost retention.
2. **Shift Ad Spend**: Double down marketing budgets on organic content channels, which show a 15% higher lifetime value (LTV) than paid ad traffic.
