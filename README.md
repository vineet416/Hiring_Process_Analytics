# Hiring Process Analytics (Excel) 

An Excel analysis of a company's hiring funnel using **7,148 interview records** (May–Aug 2014). It answers where hiring is concentrated, who gets hired, and what salaries are offered, to help a HR team decide where to focus.

## Project Files

| File | Description |
|---|---|
| [Hiring Process Analytics.xlsx](Hiring%20Process%20Analytics.xlsx) | Cleaned data, formulas, pivot table and charts |
| [Hiring Process Analytics (Report).pdf](Hiring%20Process%20Analytics%20%28Report%29.pdf) | 8-page report with methodology, charts and conclusions |

## Dataset

One row per interview decision, stored as an Excel Table on the `Table` sheet.

| Column | Description |
|---|---|
| `application_id` | Application identifier |
| `Interview Taken on` | Interview timestamp |
| `Status` | `Hired` or `Rejected` |
| `event_name` | Candidate gender (`Male`, `Female`, `Don't want to say`) |
| `Department` | 9 departments |
| `Post Name` | Job tier code (`c5`, `c9`, `i7`, ...) |
| `Offered Salary` | Offered salary (800 – 99,967) |
| `Outliers` | `TRUE` if salary is outside the 1.5×IQR fences |

## Approach

1. **Understand the data** – review structure and content.
2. **Check for missing data** – no blank values in the table.
3. **Handle outliers** – IQR method on `Offered Salary` (Q1 = 25,485.75, Q3 = 74,356.50, fences −47,820 to 147,663). No salary falls outside, so no rows were removed.
4. **Analyse** – formulas (`COUNTIFS`, `AVERAGEIF`, `QUARTILE`), a pivot table and charts.
5. **Communicate** – findings summarised in the PDF report.

## Key Insights

**Overall:** 4,683 hired and 2,465 rejected, a **65.5% hiring rate**. The average offered salary is **49,881.14**.

1. **Gender** – More men are hired (2,561 vs 1,854), but only because they are 57% of applicants. Women are hired at a higher rate (69.4% vs 62.7%).
2. **Salary** – Offers are spread almost evenly across 0 – 1,00,000 (656 – 781 per 10K band). The most common band is **40,001 – 50,000**. Average salary is the same for men and women (~49.9K).
3. **Departments** – **Operations** (2,767) and **Service** (2,047) make up 67% of applications; **Human Resource** is the smallest (97). **General Management** offers the highest average salary (55,295) and **Marketing** the lowest (48,349).
4. **Gender mix by department** – Finance and General Management applicants are ~89% female, while Operations, Sales, Marketing and Purchase skew male. This drives the overall "more males hired" result.
5. **Job tiers** – **c9** (1,790) and **c5** (1,742) are about half of all applications. `i4` (35.6%) and `c-10` (45.5%) have the lowest hiring rates.

## Tech Stack

- **Microsoft Excel** – cleaning, formulas, pivot tables, charts
- **Microsoft PowerPoint** – presenting the analysis

## How to Use

1. Open `Hiring Process Analytics.xlsx` in Excel.
2. Review the `Table` sheet; the analysis blocks (columns J:O) recalculate automatically.
3. Refresh the pivot in `Sheet6` if the data changes.
4. Read the PDF report for the full walkthrough.
