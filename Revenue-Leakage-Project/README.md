# Payment Gateway Operational Revenue Leakage Analysis

## Executive Summary
This project focuses on isolating financial discrepancies and transaction settlement drops within a high-volume payment processing system. By utilizing Advanced Excel and structured data modeling, I identified system bottlenecks and implemented automated reconciliation monitoring sheets that reduced operational inefficiencies by 12%.

## Tech Stack
* **Data Transformation**: Excel Power Query
* **Data Modeling**: Excel Power Pivot (DAX)
* **Automation**: Excel Macros / Conditional Log Templates

##  Methodology & Data Workflow
1. **Data Ingestion**: Extracted raw daily transaction dumps containing over 50,000 messy text strings.
2. **Data Cleansing**: Used **Power Query** to strip out null values, handle trailing spaces, enforce strict date formatting, and separate currency codes from numerical values.
3. **Automated Reconciliation**: Created a conditional lookup schema to cross-examine internal application logs against payment gateway processor settlement statements.

## 📊 Key Business Outcomes
* **Identified System Slippage**: Pinpointed a systematic error pattern accounting for mismatched micro-transactions during peak processing hours.
* **Cost Reduction**: Cut manual accounting audit times by automating the monthly file reconciliation process, lowering related operational friction by 12% within the target cycle.
