# HR Analytics Dashboard — Power BI

A 3-page interactive HR dashboard analyzing employee attrition, workforce profile, and performance insights using the IBM HR Analytics dataset.

---

## Dashboard Pages

### Page 1 — Attrition Overview
- Overall attrition rate, active employees, avg age
- Attrition by Department, Gender, Age Group
- Overtime vs Non-Overtime attrition rate comparison

### Page 2 — Workforce Overview
- Avg monthly income by department
- Job satisfaction by job role
- Marital status breakdown
- Distance from home vs attrition rate

### Page 3 — Performance Insights
- Avg salary hike by performance rating
- Training times by job role
- Stock option level vs attrition rate
- Job involvement vs job satisfaction

---

## Tech Stack

| Tool | Usage |
|---|---|
| PostgreSQL | Data storage + view creation |
| Power BI Desktop | Dashboard + DAX measures |
| DAX | KPIs, attrition rate, calculated columns |

---

## Data Source

[IBM HR Analytics Employee Attrition Dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset) — 1,470 employee records, 35 columns

---

## Key DAX Measures

```dax
Attrition Rate % = 
DIVIDE(
    CALCULATE(COUNTROWS('public employee_attrition_view'),
    'public employee_attrition_view'[attrition] = "Yes"),
    COUNTROWS('public employee_attrition_view'), 0
)

Active Employees = [Total Employees] - [Attrition Count]
```

---

## Key Insights

- Employees working **overtime have 3x higher attrition rate** (30.53%) vs non-overtime (10.44%)
- **18–25 age group** has the highest attrition rate at 35.77%
- **Research & Development** department has the highest attrition count (133)
- **High performers** receive significantly higher salary hike (22%) vs low performers (14%)
- **Sales department** has the highest avg monthly income (7.0K)

