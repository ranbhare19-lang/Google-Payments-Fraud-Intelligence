# Google Payments Fraud Intelligence Dashboard
<img width="1292" height="732" alt="image" src="https://github.com/user-attachments/assets/562caf3f-2e08-4bbf-bcc5-5148e5517e06" />


## Project Overview
End-to-end SQL fraud risk analysis on 590,540 IEEE-CIS transactions identifying 
$3,083,844 in fraud exposure with a weighted risk scoring model and window functions.
Built to mirror analytical workflows used in payments risk management.

## Business Problem
Payment fraud costs companies billions annually. This project identifies WHERE fraud 
is happening, HOW MUCH it costs, and WHICH transactions the risk team should 
investigate first — ranked by a cumulative risk scoring model.

## Key Findings
- 20,663 fraudulent transactions identified — 3.5% fraud rate
- $3,083,844 total fraud exposure value
- anonymous.com email domain = strongest fraud signal (flagged as Priority 1)
- Visa accounts for 64.7% of fraud by volume
- Debit cards slightly exceed credit cards in fraud count
- Average fraud transaction ($149) is $14.73 higher than legitimate ($134)
- Top 4 highest risk transactions scored 60/85 on risk model

## Advanced SQL Techniques Used
- INNER JOIN across two tables (590,540 + 144,233 records)
- Cumulative CASE WHEN risk scoring model
- RANK() window function for investigation prioritization
- Multi-condition WHERE filtering
- Aggregate functions — COUNT, SUM, AVG

## Tools Used
- SQL Server (SSMS) — data storage and analysis
- Looker Studio — dashboard and visualization
- DAX — KPI measures

## Dataset
IEEE-CIS Fraud Detection Dataset
Source: Kaggle Competition
Size: 590,540 transactions, 144,233 identity records, 435 total columns

## Business Recommendations
1. Auto-flag all transactions from anonymous.com email domain
2. Trigger manual review for transactions scoring above 40 on risk model
3. Priority investigation for transactions scoring 60+ — block immediately
4. Monitor debit card transactions above $500 as high-risk combination
