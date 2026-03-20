# 🛒 Ecommerce Analytics — Full Analysis

> End-to-end data analytics + ML pipeline on Olist Brazilian E-Commerce — 
> 9 tables, 96,454 orders, churn prediction with Random Forest.

![Python](https://img.shields.io/badge/Python-3.11-blue?style=flat-square&logo=python)
![FastAPI](https://img.shields.io/badge/FastAPI-Latest-green?style=flat-square&logo=fastapi)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-blue?style=flat-square&logo=postgresql)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue?style=flat-square&logo=docker)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?style=flat-square&logo=scikitlearn)
![Status](https://img.shields.io/badge/Stage-v0_Complete-green?style=flat-square)

---

## 📋 Table of Contents

- [What This Does](#-what-this-does)
- [Real Numbers](#-real-numbers)
- [Architecture](#-architecture)
- [Project Structure](#-project-structure)
- [What I Built](#-what-i-built)
- [RFM Segments](#-rfm-segments)
- [Quick Start](#-quick-start)
- [Environment Variables](#-environment-variables)
- [API Overview](#-api-overview)
- [Tech Stack](#-tech-stack)
- [Version Roadmap](#-version-roadmap)
- [Author](#-author)

---

## 🧠 What This Does

Olist is a real Brazilian e-commerce company.
This project takes their raw 9-table dataset and answers real business questions
using the full data analyst toolkit.

1. **Problem** — Business has 93,335 customers but no visibility into who will churn, which categories drive revenue, or where to focus sales effort
2. **Solution** — Full EDA pipeline + RFM segmentation + CLV calculation + ML churn prediction with 98.74% churn rate detected
3. **For** — Data Analyst / ML Analyst hiring managers looking for end-to-end project proof

**Current Status:** `v0` — Data cleaned. EDA complete. ML model trained. FastAPI in progress.

---

## 📊 Real Numbers

| Metric | Value |
|--------|-------|
| Total Revenue | R$16,110,492 |
| Total Profit | R$5,061,907 |
| Profit Margin | 32.3% |
| Total Orders | 96,454 |
| Unique Customers | 93,335 |
| Top Category | beleza_saude (Health & Beauty) |
| Top State | SP — R$6,041,602 (37.5% revenue) |
| States Analyzed | 27 |
| Categories Analyzed | 74 |
| Date Range | October 2016 – August 2018 |
| High Risk Customers | 90,535 |
| Champions | 141 |
| Lost Customers | 45,822 |
| Overall Churn Rate | 98.74% |
| Best ML Model | Random Forest |

---

## 🏗️ Architecture
```
Raw 9 CSV Tables (Olist)
      ↓
Python + Pandas (Clean + Merge)
      ↓
Master DataFrame (df.csv)
      ↓
7 Analysis Pipelines (EDA + Charts)
      ↓
RFM + CLV + Churn Features
      ↓
Random Forest Model → churn_model.pkl
      ↓
FastAPI /predict endpoint
      ↓
React Vite Frontend (Portfolio)
```

Full system design → [HLD.md](./HLD.md)

---

## 🗂️ Project Structure

| File / Folder | What It Covers |
|---|---|
| [README.md](./README.md) | You are here |
| [HLD.md](./HLD.md) | Big picture architecture — boxes and arrows |
| [LLD.md](./LLD.md) | Every function, formula, ML design detail |
| [API_CONTRACTS.md](./API_CONTRACTS.md) | Every endpoint — request, response, errors |
| [SCHEMA.md](./SCHEMA.md) | All 9 tables — columns, indexes, plain English |
| [schema_stage0.sql](./schema_stage0.sql) | Raw SQL — create all v0 tables |
| [ERD.png](./ERD.png) | Visual diagram — all 9 table relationships |
| [BUSINESS_INSIGHTS.md](./BUSINESS_INSIGHTS.md) | 6 real business problems + revenue strategy |
| [docker-compose.yml](./docker-compose.yml) | One command spins up PostgreSQL locally |
| [RUNBOOK.md](./RUNBOOK.md) | Deploy, rollback, restart, 3am incident fixes |
| [SCALE_GUIDE.md](./SCALE_GUIDE.md) | Stack decisions from 0 to 1 billion users |
| [SCALING_QUESTIONS.md](./SCALING_QUESTIONS.md) | 20 questions to ask before any feature |
| [VERSION_ROADMAP.md](./VERSION_ROADMAP.md) | v0 → v4 plan with mindset per stage |
| [ADR/](./ADR/) | One file per major architecture decision |
| [notebooks/](./notebooks/) | All 7 EDA pipelines — Jupyter notebooks |
| [sql/](./sql/) | 60 SQL questions on all 9 tables |
| [MsExcel_Dashboard/](./MsExcel_Dashboard/) | Excel pivot tables + slicers |
| [Powerbi_dashboard/](./Powerbi_dashboard/) | Power BI — all 9 tables connected |

---

## 🔨 What I Built

### 1. Data Cleaning
- Loaded all 9 raw CSV tables
- Fixed 5 datetime columns
- Handled nulls — dropped critical rows, filled medians
- Removed duplicates
- Merged all 9 tables into one master dataframe
- Engineered 15+ features (revenue, profit, margin, delay, freight ratio)

### 2. EDA — 7 Pipelines
- Pipeline 1 — Data load and cleaning
- Pipeline 2 — Build all summary tables (monthly, category, state, RFM, CLV, pareto)
- Pipeline 3 — Static performance charts (Matplotlib)
- Pipeline 4 — Static product and regional charts (Matplotlib)
- Pipeline 5 — Static customer intelligence charts (Matplotlib)
- Pipeline 6 — Interactive charts (Plotly)
- Pipeline 7 — Executive KPI dashboard (Plotly)

### 3. Key Analyses
- Monthly revenue and profit trends (Oct 2016 – Aug 2018)
- Top 10 categories by revenue and profit
- 80/20 Pareto analysis
- Customer cohort analysis — retention over time
- RFM segmentation — 5 segments
- Customer Lifetime Value (CLV) for all 93,335 customers
- State-wise revenue across all 27 states

### 4. SQL — 60 Questions
- Covers SELECT, JOIN, GROUP BY, HAVING
- Subqueries, CTEs, window functions
- RANK, running totals, YoY growth

### 5. Excel Analysis
- Pivot tables for category and monthly breakdowns
- Slicers for interactive filtering
- KPI summary sheet

### 6. Power BI Dashboard
- All 9 tables connected with proper relationships
- Interactive KPI cards, slicers, bar/line charts
- Filter by date, category, state, seller

### 7. Machine Learning — Churn Prediction
- Defined churn: customer with no repeat order
- Features: recency, frequency, monetary, avg profit,
  avg freight, avg price, total items, installments, days active
- Models: Logistic Regression, Decision Tree, Random Forest
- Best model: Random Forest
- Output: churn_probability (0.0–1.0) + risk label (High/Medium/Low)

---

## 👥 RFM Customer Segments

| Segment | Customers | Total Revenue | Avg CLV | Churn Rate |
|---------|-----------|---------------|---------|------------|
| Champions | 141 | R$78,577 | R$2,174 | 0% |
| Loyal | 1,408 | R$427,886 | R$608 | 0% |
| At Risk | 672 | R$218,009 | R$696 | 0% |
| Lost | 45,822 | R$7,777,151 | R$174 | 98.74% |

---

## ⚡ Quick Start

**Prerequisites:** Python 3.11+, Docker, Git
```bash
# 1. Clone the repo
git clone https://github.com/Ashutosh-AIBOT/ecommerce-analytics.git
cd ecommerce-analytics

# 2. Create virtual environment
python -m venv venv
source venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Set up environment variables
cp .env.example .env

# 5. Start database
docker-compose up -d

# 6. Run notebooks in order
jupyter notebook notebooks/

# 7. Start FastAPI server
uvicorn api.app:app --reload

# 8. Open API docs
# http://localhost:8000/docs
```

---

## 🔑 Environment Variables

| Variable | What It Is | Example |
|---|---|---|
| `DATABASE_URL` | PostgreSQL connection string | `postgresql://user:pass@localhost:5432/olist` |
| `MODEL_PATH` | Path to saved pkl file | `./api/model/churn_model.pkl` |
| `ENVIRONMENT` | App environment | `development` |

---

## 📡 API Overview

| Method | Endpoint | What It Does |
|---|---|---|
| `GET` | `/health` | Health check |
| `POST` | `/predict` | Returns churn probability for a customer |

Full contracts → [API_CONTRACTS.md](./API_CONTRACTS.md)

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.11 | Data cleaning, EDA, ML |
| Pandas + NumPy | Data manipulation |
| Matplotlib + Seaborn | Static charts |
| Plotly | Interactive charts |
| Scikit-learn | ML models |
| PostgreSQL | SQL analysis |
| Excel | Pivot tables, KPIs |
| Power BI | BI dashboard |
| FastAPI | Serve churn model as API |
| Docker | Run PostgreSQL locally |

---

## 📌 Version Roadmap

| Version | What Gets Built |
|---|---|
| `v0` ← **you are here** | Data cleaned. EDA done. ML trained. FastAPI in progress. |
| `v1` | 🔜 Coming Soon |
| `v2` | 🔜 Coming Soon |
| `v3` | 🔜 Coming Soon |

Full breakdown → [VERSION_ROADMAP.md](./VERSION_ROADMAP.md)

---

## 📊 Project Status

| Deliverable | Status |
|-------------|--------|
| Data Cleaning | ✅ Complete |
| EDA + 7 Pipelines | ✅ Complete |
| Excel Analysis | ✅ Complete |
| SQL 60 Questions | ✅ Complete |
| Power BI Dashboard | ✅ Complete |
| ML Churn Prediction | ✅ Complete |
| Documentation | ✅ Complete |
| FastAPI Backend | 🔄 In Progress |
| React Frontend | 🔄 In Progress |

---

## 🔗 Related Repos

| Part | GitHub |
|---|---|
| 📊 Backend + Data + ML (this repo) | [ecommerce-analytics](https://github.com/Ashutosh-AIBOT/ecommerce-analytics) |
| 💻 Frontend | [ecommerce-analytics_frontend](https://github.com/Ashutosh-AIBOT/ecommerce-analytics_frontend) |

---

## 👤 Author

**Ashutosh**
[GitHub](https://github.com/Ashutosh-AIBOT) · [LinkedIn](https://www.linkedin.com/in/ashutosh1975271/)

---

> *"Everyone said get experience first.  
> I said — let the project speak."*
>
> — Ashutosh, building this from zero.
