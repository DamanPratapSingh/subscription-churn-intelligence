# 📉 Subscription Churn Intelligence

An end-to-end data analytics project that simulates, cleans, analyzes, and visualizes subscription customer churn for a SaaS business — combining Python (Pandas, NumPy) with Power BI for business intelligence reporting.

---

## 🧠 Project Overview

Customer churn is one of the most critical metrics for any subscription-based business. This project builds a complete churn intelligence pipeline — from synthetic dataset generation with intentional data quality issues, through cleaning and EDA, to an interactive Power BI dashboard for business stakeholders.

---

## 📁 Project Structure

```
subscription_churn_intelligence/
├── data/
│   ├── subscription_churn_raw.csv       # Raw dataset (with noise, nulls, duplicates)
│   └── subscription_churn_clean.csv     # Cleaned & processed dataset
├── notebooks/
│   └── churn_dataset_generation.ipynb   # Data generation, cleaning & EDA
├── dashboard/
│   └── churn_analysis.pbix              # Power BI interactive dashboard
└── outputs/                             # Reserved for exported charts/reports
```

---

## 🔄 Pipeline

### 1. 🏗️ Dataset Generation
- Synthetically generated **10,000 customer records** using NumPy and Pandas
- Introduced realistic data quality issues:
  - Inconsistent casing (`basic`, `BASIC`, `Basic`)
  - Abbreviations (`NA` instead of `North America`)
  - Missing values in `device_type` and `support_tickets`
  - Negative values in `usage_hours_per_week`
  - 50 intentional duplicate rows

### 2. 🧹 Data Cleaning
- Removed duplicate records
- Standardized `subscription_plan` using `.str.title()`
- Replaced region abbreviations with full names
- Filled nulls: `device_type → "Unknown"`, `support_tickets → 0`
- Clipped negative usage hours to 0
- Recalculated `monthly_fee` and `total_revenue` after cleaning

### 3. 📊 Exploratory Data Analysis (EDA)
- Overall churn rate calculation
- Churn breakdown by subscription plan, region, and device type
- Revenue impact analysis of churned vs active customers
- Usage behavior patterns among churned customers

### 4. 📈 Power BI Dashboard
- Interactive filters by plan, region, and device type
- Churn rate KPIs and trend analysis
- Revenue vs churn correlation visuals
- Cancellation reason breakdown

---

## 📌 Key Dataset Features

| Column | Description |
|---|---|
| `customer_id` | Unique customer identifier |
| `subscription_plan` | Basic / Standard / Premium / Enterprise |
| `region` | North America / Europe / Asia / South America |
| `device_type` | Mobile / Desktop / Tablet |
| `usage_hours_per_week` | Weekly platform usage |
| `support_tickets` | Number of support tickets raised |
| `customer_lifetime_month` | Months since subscription start |
| `monthly_fee` | Plan fee (₹25 – ₹150) |
| `total_revenue` | Lifetime revenue generated |
| `churn_flag` | 1 = Churned, 0 = Active |
| `cancellation_reason` | Too Expensive / Low Usage / Better Alternative / Technical Issues |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3 | Data generation & cleaning |
| Pandas | Data manipulation |
| NumPy | Synthetic data & churn logic |
| Jupyter Notebook | Analysis & EDA |
| Power BI | Business intelligence dashboard |

---

## 🚀 How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/DamanPratapSingh/subscription-churn-intelligence.git
   cd subscription-churn-intelligence
   ```

2. Install dependencies:
   ```bash
   pip install pandas numpy jupyter
   ```

3. Open the notebook:
   ```bash
   jupyter notebook notebooks/churn_dataset_generation.ipynb
   ```

4. To view the dashboard, open `dashboard/churn_analysis.pbix` in **Power BI Desktop**

---

## 👤 Author

**Daman Pratap Singh**  
B.Tech Computer Science (AI/ML) — GLA University, Mathura  
[GitHub](https://github.com/DamanPratapSingh) • [LinkedIn](https://linkedin.com/in/your-linkedin-here)
