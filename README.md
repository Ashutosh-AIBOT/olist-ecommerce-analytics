# E-Commerce Sales & Customer Analytics
### Olist Brazilian E-Commerce Dataset | End-to-End Data Analytics Project

> Built by **Ashutosh** — Fresher targeting Data Analyst / ML Analyst roles (2026)

---

## What Is This Project?

Olist is a real Brazilian e-commerce company.
This project takes their raw 9-table dataset and answers real business questions
using the full data analyst toolkit — Python, SQL, Excel, Power BI, and ML.

---

## Business Questions Answered

- Which products and categories generate 80% of revenue?
- How are monthly revenue and orders trending over time?
- Which customers are Champions, Loyal, At Risk, or Lost?
- What is each customer's lifetime value (CLV)?
- Which customers will churn — and with what probability?

---

## Dataset

**Source:** https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

| Table | Description |
|-------|-------------|
| olist_orders | All orders and their status |
| olist_order_items | Products inside each order |
| olist_products | Product details and dimensions |
| olist_customers | Customer location info |
| olist_sellers | Seller location info |
| olist_order_payments | Payment type, installments, value |
| olist_order_reviews | Customer review scores and comments |
| olist_geolocation | Zip code to lat/lng mapping |
| product_category_name_translation | Portuguese to English category names |

---

## Key Results

| Metric | Value |
|--------|-------|
| Total Revenue | R$16,110,492 |
| Total Profit | R$5,061,907 |
| Total Orders Analyzed | 96,454 |
| Total Unique Customers | 93,335 |
| Average Profit Margin | 32.3% |
| Top Revenue Category | beleza_saude (Health & Beauty) |
| Top Revenue State | SP — R$6,041,602 |
| States Analyzed | 27 |
| Categories Analyzed | 74 |
| Date Range | October 2016 – August 2018 |
| Customers Predicted for Churn | 93,335 |
| High Risk Customers | 90,535 |
| Best ML Model | Random Forest |

---

## What I Built

### 1. Data Cleaning (Python + Pandas)
- Loaded all 9 raw CSV tables
- Fixed 5 datetime columns
- Handled null values — dropped critical rows, filled medians
- Removed duplicates
- Merged all 9 tables into one master dataframe
- Engineered 15+ new features (revenue, profit, margin, delay, freight ratio)

### 2. Exploratory Data Analysis — 7 Pipelines
- Pipeline 1 — Data load and cleaning
- Pipeline 2 — Build all summary tables (monthly, category, state, RFM, CLV, pareto)
- Pipeline 3 — Static performance charts (Matplotlib)
- Pipeline 4 — Static product and regional charts (Matplotlib)
- Pipeline 5 — Static customer intelligence charts (Matplotlib)
- Pipeline 6 — Interactive charts (Plotly)
- Pipeline 7 — Executive KPI dashboard (Plotly)

### 3. Key Analyses Done
- Monthly revenue and profit trends (Oct 2016 – Aug 2018)
- Top 10 categories by revenue and profit
- 80/20 Pareto analysis (which 20% products = 80% revenue)
- Customer cohort analysis — retention over time
- RFM segmentation — 5 segments (Champions, Loyal, At Risk, Lost, New)
- Customer Lifetime Value (CLV) for all 93,335 customers
- State-wise revenue and performance across all 27 states

### 4. Excel Analysis
- Pivot tables for category and monthly breakdowns
- Slicers for interactive filtering
- KPI summary sheet with key business metrics

### 5. SQL Analysis
- 60 questions solved on all 9 tables
- Covers: SELECT, JOIN, GROUP BY, HAVING, subqueries,
  CTEs, window functions, RANK, running totals, YoY growth

### 6. Power BI Dashboard
- All 9 tables connected with proper relationships
- Interactive KPI cards, slicers, bar/line charts
- Filter by date, category, state, seller

### 7. Machine Learning — Churn Prediction
- Defined churn: customer with no repeat order in dataset
- Features: recency, frequency, monetary, avg profit,
  avg freight, avg price, total items, installments, days active
- Models trained: Logistic Regression, Decision Tree, Random Forest
- Best model: Random Forest (highest accuracy + F1 score)
- Output: churn_probability (0.0–1.0) + churn_risk label (High/Medium/Low)

---

## RFM Customer Segments

| Segment | Customers | Total Revenue | Avg CLV | Churn Rate |
|---------|-----------|---------------|---------|------------|
| Champions | 141 | R$78,577 | R$2,174 | 0% |
| Loyal | 1,408 | R$427,886 | R$608 | 0% |
| At Risk | 672 | R$218,009 | R$696 | 0% |
| Lost | 45,822 | R$7,777,151 | R$174 | 98.74% |

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3 | Data cleaning, EDA, ML |
| Pandas + NumPy | Data manipulation and feature engineering |
| Matplotlib + Seaborn | Static charts (7 pipelines) |
| Plotly | Interactive charts and dashboard |
| Scikit-learn | ML models (Logistic Regression, Decision Tree, Random Forest) |
| SQL (PostgreSQL) | 60 analysis questions |
| Excel | Pivot tables, slicers, KPI reporting |
| Power BI | Business intelligence dashboard |
| Streamlit | Live churn prediction app |
| Git + GitHub | Version control and portfolio |

---

## Folder Structure

```
ecommerce-analytics/
├── data/
│   ├── raw/                        ← Original 9 CSV files (never modified)
│   └── processed/                  ← Cleaned and merged output files
├── notebooks/
│   ├── Full-Analysis.ipynb         ← Main EDA + all 7 pipelines
│   └── matplotlib-pipeline.ipynb  ← Chart pipeline
├── sql/
│   └── 60_questions.sql            ← All 60 SQL queries
├── dashboard/
│   └── olist_dashboard.pbix        ← Power BI dashboard file
├── docs/
│   ├── HLD.md                      ← High level system design
│   └── LLD.md                      ← Detailed feature-level design
├── model/
│   ├── churn_model.pkl             ← Saved Random Forest model
│   └── app.py                      ← Streamlit prediction app
├── portfolio/
│   └── index.html                  ← Portfolio website
├── requirements.txt
└── README.md
```

---

## How to Run Locally

```bash
# 1. Clone the repo
git clone https://github.com/YOUR_USERNAME/ecommerce-analytics
cd ecommerce-analytics

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run notebooks in order
jupyter notebook notebooks/

# 4. Run live churn prediction app
streamlit run model/app.py
```

---

## Project Status

| Deliverable | Status |
|-------------|--------|
| Data Cleaning | ✅ Complete |
| EDA + 7 Pipelines | ✅ Complete |
| Excel Analysis | ✅ Complete |
| SQL 60 Questions | ✅ Complete |
| Power BI Dashboard | ✅ Complete |
| ML Churn Prediction | ✅ Complete |
| Documentation (HLD + LLD) | ✅ Complete |
| Portfolio Website | 🔄 In Progress |
| Live Model Hosted | 🔄 In Progress |

---

## Connect

- GitHub: https://github.com/Ashutosh-Aibot
- LinkedIn: https://linkedin.com/in/YOUR_PROFILE