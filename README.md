# HR Employee Attrition Analysis

## Overview
End-to-end HR analytics project analyzing employee attrition using IBM's published 
HR Analytics dataset (1,470 employees, 35 features). The goal: identify who is leaving, 
why they are leaving, and translate findings into actionable retention recommendations.

## Tools Used
- **Python** — pandas, numpy (data cleaning & feature engineering)
- **SQL Server Express** — business-question SQL queries via SQLAlchemy/pyodbc
- **Power BI Desktop** — DAX measures, interactive dashboard
- **Jupyter Notebook**

## Key Findings
- **Overall attrition rate: 16.1%** (237 out of 1,470 employees)
- **Sales department** has the highest attrition (20.6%), driven specifically by Sales Representatives at 40%+
- **Overtime employees churn at 30.5%** — nearly 3x the rate of non-overtime employees (10.4%)
- **Low-income employees** churn at 29.3% vs 10.3% for the highest earners — attrition drops sharply as income rises
- **Compound overwork risk** (overtime + poor work-life balance) pushes attrition to 33.3%

## SQL Highlights
- Conditional aggregation using `SUM(CASE WHEN...)` for attrition rate calculations
- `GROUP BY` segmentation across department, overtime, income band, and job role
- `RANK() OVER (PARTITION BY JobRole)` window function to rank earners within each role

## Recommendations
1. Investigate and address workload/overtime in Sales — particularly for Sales Representatives
2. Review compensation structure for low-income employees, where attrition is nearly 3x higher
3. Launch re-engagement programs for overworked employees before they disengage entirely

## Files
- `Hr_Attrition_Analysis.ipynb` — full Python + SQL analysis notebook
- `HR_Attrition_Analysis.pbix` — Power BI dashboard file
- `WA_Fn-UseC_-HR-Employee-Attrition.csv` — dataset (source: IBM/Kaggle)
