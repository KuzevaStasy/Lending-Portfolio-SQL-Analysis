# 🏦 Lending Portfolio SQL Analysis

> SQL-driven business analytics on a synthetic lending portfolio — built with SQLite, Python, and Jupyter Notebook.

---

## 📌 Project Overview

This project simulates a fintech lending portfolio database and uses SQL to answer real credit risk business questions.

The goal is to demonstrate how a Business Analyst or Credit Risk Analyst uses structured data to monitor portfolio health, identify high-risk segments, and support management decisions.

**Business questions answered:**
- What is the overall portfolio default rate?
- Which loan types and customer segments carry the highest risk?
- How does income level and employment type affect default probability?
- Which regions show the highest payment overdue rates?
- What are the monthly loan origination trends?

> ⚠️ All data is synthetically generated for portfolio demonstration purposes. No real customer data is used.

---

## 🗂️ Database Schema

The SQLite database contains 3 tables:

```
customers          loans                payments
──────────         ──────────           ──────────
customer_id   ──►  loan_id         ──►  payment_id
age                customer_id          loan_id
annual_income      loan_type            payment_date
employment_type    loan_amount          amount_paid
region             interest_rate        days_overdue
credit_score       term_months
                   issue_date
                   status
```

---

## 📊 SQL Queries Covered

| # | Query | SQL Concepts |
|---|-------|-------------|
| 1 | Portfolio overview — total loans, exposure, default rate | `COUNT`, `SUM`, `AVG`, `CASE WHEN` |
| 2 | Default rate by loan type | `GROUP BY`, `ORDER BY` |
| 3 | Risk by employment type | `JOIN` (2 tables), `GROUP BY` |
| 4 | Default rate by income bracket | `JOIN`, `CASE WHEN` segmentation |
| 5 | Monthly origination trend | `SUBSTR`, `GROUP BY` on date |
| 6 | High-risk customers with multiple loans | `Subquery`, `HAVING`, `JOIN` |
| 7 | Average days overdue by region | `JOIN` across 3 tables |

---

## 💡 Key Business Insights

- **Employment type is a primary risk driver** — unemployed and self-employed customers show significantly higher default rates
- **Lower income segments** (< €25K) carry the highest default probability, highlighting the need for affordability checks
- **Regional payment behaviour** varies — certain regions show consistently higher days overdue, suggesting local economic risk factors
- **Revenue growth ≠ portfolio health** — rapid origination growth can mask rising default risk if not monitored in parallel

---

## 🛠️ Tools & Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge&logo=python&logoColor=white)

---

## ▶️ How to Run

**Requirements:**
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

> SQLite is built into Python — no additional installation needed.

**Steps:**
1. Clone the repository
   ```bash
   git clone https://github.com/KuzevaStasy/Lending-Portfolio-SQL-Analysis.git
   cd Lending-Portfolio-SQL-Analysis
   ```
2. Launch Jupyter Notebook
   ```bash
   jupyter notebook
   ```
3. Open `Lending_Portfolio_SQL_Analysis.ipynb`
4. Run all cells (`Kernel → Restart & Run All`)

The synthetic database (`lending_portfolio.db`) is generated automatically on first run.

---

## 📁 Project Structure

```
Lending-Portfolio-SQL-Analysis/
│
├── Lending_Portfolio_SQL_Analysis.ipynb   # Main analysis notebook
├── lending_portfolio.db                   # Auto-generated SQLite database
└── README.md
```

---

## 🔮 Possible Next Steps

- Add SQL window functions (`RANK`, `LAG`, `LEAD`) for cohort analysis
- Build a cohort default rate tracker by origination month
- Connect to Power BI or Tableau for interactive dashboards
- Extend schema with a `collections` table to model recovery rates

---

## 👤 Author

**Stanislava Kuzeva**  
Business Analytics & Credit Risk  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/stanislava-kuzeva-b1757241/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/KuzevaStasy)

---

*Built as a portfolio project to demonstrate SQL analytics and credit risk thinking in a fintech context.*
