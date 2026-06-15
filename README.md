<div align="center">

<img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/Pandas-Data%20Wrangling-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
<img src="https://img.shields.io/badge/Plotly-Interactive%20Viz-3F4F75?style=for-the-badge&logo=plotly&logoColor=white"/>
<img src="https://img.shields.io/badge/SQL-Analytics-4479A1?style=for-the-badge&logo=mysql&logoColor=white"/>
<img src="https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge"/>

# 🛒 CartIQ — Retail Intelligence from Instacart Transaction Data

**A full-stack data science pipeline that transforms millions of raw grocery transactions into strategic business decisions — covering customer behavior, inventory signals, and loyalty segmentation.**

[**View Demo**](#) · [**Datasets](#-datasets) · [**Report Bug**](#) · [**Request Feature**](#)

---

</div>

## 📌 The Problem

Retail businesses sit on mountains of transaction data but rarely extract its full value. Questions like *"Which products drive repeat purchases?"*, *"When do customers churn?"*, and *"What should we stock more of on Sundays?"* go unanswered — not for lack of data, but lack of structure.

**CartIQ answers those questions systematically**, using Instacart's real-world order history to surface patterns that directly inform marketing, inventory, and customer retention strategy.

---

## 🏗️ Pipeline Overview

```
Raw Transaction Data (orders.csv + order_products_prior.csv)
        │
        ▼
┌────────────────────────┐
│  Data Cleaning &       │  ← Null handling, deduplication,
│  Preprocessing         │    type normalization, merge logic
└──────────┬─────────────┘
           │
           ▼
┌────────────────────────┐
│  Exploratory Data      │  ← Descriptive stats, time-series trends,
│  Analysis (EDA)        │    basket analysis, reorder behavior
└──────────┬─────────────┘
           │
           ▼
┌────────────────────────┐
│  Segmentation &        │  ← Customer loyalty tiers, product affinity,
│  Business Insights     │    demand forecasting signals
└──────────┬─────────────┘
           │
           ▼
┌────────────────────────┐
│  Interactive Dashboard │  ← Visual KPIs, drill-down charts,
│                        │    executive-ready summary views
└────────────────────────┘
```

---

## 🔬 Analysis Dimensions

### 🕐 Temporal Behavior
- Peak order hours and days of the week — with heatmap breakdowns
- Monthly sales volume trends and seasonal demand shifts
- Days-since-prior-order distribution to identify churn risk windows

### 🛍️ Product Intelligence
- Top 20 most reordered products and their reorder rate
- Department and aisle-level performance ranking
- First-order vs. repeat-order product mix analysis

### 👤 Customer Segmentation
- Loyalty tiers based on order frequency and basket size
- Identification of high-value customers driving disproportionate revenue
- Churn indicators based on order gap patterns

### 📦 Inventory Signals
- High-demand products with consistently high reorder rates → stock priority candidates
- Low-reorder, high-volume items → potential one-time promotion products
- Department-level demand variability for supply chain planning

---

## 📊 Dashboard Preview

<img width="712" height="566" alt="CartIQ Dashboard" src="https://github.com/user-attachments/assets/4c639458-f04e-47f4-9bdc-b556dc349b79"/>

The interactive dashboard surfaces:
- **Order volume trends** by hour, day, and month
- **Top products and departments** by order count and reorder rate
- **Customer loyalty distribution** across segments
- **Basket size analysis** and purchase frequency heatmaps

---

## 💡 Key Business Insights

| Area | Finding | Recommendation |
|---|---|---|
| **Peak Demand** | Orders spike Sunday 10AM–12PM | Schedule promotions and flash sales in this window |
| **Reorder Champions** | Bananas, whole milk, and eggs have >60% reorder rate | Never let these go out of stock — auto-replenishment candidates |
| **Loyal Customers** | Top 10% of users account for ~40% of total orders | Build a VIP loyalty program targeting this cohort |
| **Churn Signal** | 30+ day order gaps correlate with customer drop-off | Trigger win-back emails at the 21-day inactivity mark |
| **New User Behavior** | First orders skew toward fresh produce | Design onboarding offers around high-margin fresh items |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Data Wrangling | `pandas` · `numpy` |
| Analysis & Stats | `scipy` · `statsmodels` |
| Visualization | `matplotlib` · `seaborn` · `plotly` |
| Dashboard | `Plotly Dash` / `Streamlit` |
| Query Layer | `SQL` (via `pandasql` / `SQLite`) |
| Environment | `Python 3.10+` · `Jupyter Notebooks` |

---

## 📂 Datasets

This project uses two Instacart datasets. Download and place both in the `/data` folder before running any notebooks.

| File | Description | Link |
|---|---|---|
| `orders.csv` | Customer order history with timestamps and frequency | [Download](https://drive.google.com/file/d/17n_c6GVoPmXK4PB5FTSz_7j3lwhpAU6_/view?usp=sharing) |
| `order_products_prior.csv` | Product-level detail for each prior order | [Download](https://drive.google.com/file/d/1j6HodLJPPB8bkUh8b9KihKBNGsKa1mXh/view?usp=sharing) |

> ⚠️ Both files must be in the same `/data` directory before running any notebooks or scripts.

---

## 🚀 Quickstart

```bash
# 1. Clone the repository
git clone https://github.com/your-username/cartiq.git
cd cartiq

# 2. Install dependencies
pip install -r requirements.txt

# 3. Add datasets to /data folder
# (Download from the links above)

# 4. Run the analysis pipeline
jupyter notebook notebooks/01_eda.ipynb

# 5. Launch the dashboard
streamlit run app/dashboard.py
```

---

## 📁 Project Structure

```
cartiq/
│
├── data/
│   ├── orders.csv                     # Customer order records
│   └── order_products_prior.csv       # Product-level order detail
│
├── notebooks/
│   ├── 01_preprocessing.ipynb         # Cleaning, merging, type fixes
│   ├── 02_eda.ipynb                   # Exploratory analysis & stats
│   ├── 03_segmentation.ipynb          # Customer loyalty segmentation
│   └── 04_insights.ipynb              # Business recommendations
│
├── src/
│   ├── clean.py                       # Data preprocessing functions
│   ├── analyze.py                     # Core analysis logic
│   └── visualize.py                   # Chart generation utilities
│
├── app/
│   └── dashboard.py                   # Interactive dashboard
│
├── outputs/
│   └── charts/                        # Exported visualizations
│
├── requirements.txt
└── README.md
```

---

## 🔭 Roadmap

- [ ] Add product association rules using Apriori / FP-Growth (market basket analysis)
- [ ] Integrate RFM scoring (Recency, Frequency, Monetary) for customer ranking
- [ ] Build a product recommendation engine using collaborative filtering
- [ ] Deploy dashboard to Streamlit Cloud / Heroku
- [ ] Add SQL query layer for on-demand ad-hoc reporting

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

---

<div align="center">

**Built to show that great business decisions start with clean data and clear thinking.**

⭐ If this helped you or inspired your own project, drop a star — it means a lot.

</div>


