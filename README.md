# 📊 Vendor Performance Analysis

A data-driven analysis of vendor and brand performance in the retail and wholesale industry. This project helps businesses identify underperforming brands, optimize pricing strategies, assess bulk purchasing impact, and reduce vendor dependency risk to improve overall profitability.

---

## 🎯 Business Problem

Companies in retail and wholesale face recurring challenges:

- Losses from inefficient pricing or procurement decisions
- Overstocking and poor inventory turnover
- Over-reliance on a small group of vendors
- Profitability variance between high- and low-performing vendors

This project addresses all four using SQL-based data extraction, Python-driven EDA, and actionable business insights.

---

## 🔍 Key Findings

| Insight | Finding |
|---|---|
| Brands needing promotion | 198 brands with high margins but low sales |
| Vendor concentration risk | Top 10 vendors = 65.7% of total purchases |
| Bulk purchase savings | 72% lower unit cost ($10.78/unit) for large orders |
| Top vendor by sales | Diageo North America Inc. — $68M sales, $17.89M gross profit |
| Top brand by sales | Jack Daniels No 7 Black — $7.96M |
| Purchase price vs profit | Correlation of -0.016 — purchase price barely affects profit |
| Sales price vs margin | Negative correlation (-0.179) — higher price shrinks margins |
| Stock turnover vs profit | Weak correlation (-0.038) — faster turnover ≠ higher profit |

---

## ⚙️ How It Works

1. **Data Ingestion** — Raw CSV files loaded into SQLite via chunked ingestion pipeline (`ingesting_db.py`)
2. **Vendor Summary** — Multi-table SQL joins (purchases, sales, invoices) to build a unified `vendor_sales_summary` table
3. **Feature Engineering** — Derived columns: `GrossProfit`, `ProfitMargin`, `StockTurnover`, `SalesToPurchaseRatio`
4. **Data Cleaning** — Removed zero/negative sales, profit margins, and unsold inventory
5. **EDA** — Distribution plots, boxplots, correlation heatmaps via Seaborn and Matplotlib
6. **Analysis** — Answered 5 core business questions using grouped aggregations and threshold-based filtering

---

## 🛠️ Tech Stack

| Layer | Tool |
|---|---|
| Language | Python 3 |
| Data Analysis | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Database | SQLite (via sqlite3 + SQLAlchemy) |
| Statistical Analysis | SciPy |
| Notebook | Jupyter Notebook |
| Data Input | CSV / Excel |

---

## 📁 Project Structure

```
vendor-performance-analysis/
├── data/                          # Raw CSV input files
├── logs/                          # Ingestion and processing logs
├── ingesting_db.py                # CSV → SQLite ingestion pipeline
├── get_vendor_summary.py          # SQL joins + feature engineering
├── Exploratory_Data_Analysis.ipynb
├── Vendor_Performance_Analysis.ipynb
├── vendor_sales_summary_filtered.csv
├── Business_Problem_Report.docx   # Full findings report
└── README.md
```

---

## 📦 Installation

```bash
git clone https://github.com/yourusername/vendor-performance-analysis.git
cd vendor-performance-analysis
pip install -r requirements.txt
```

**Requirements:**
```
pandas
numpy
matplotlib
seaborn
scipy
sqlalchemy
jupyter
openpyxl
```

---

## 🚀 Usage

**Step 1 — Ingest raw data into SQLite:**
```bash
python ingesting_db.py
```

**Step 2 — Build vendor summary table:**
```bash
python get_vendor_summary.py
```

**Step 3 — Run analysis notebooks:**
```bash
jupyter notebook
```
Open `Exploratory_Data_Analysis.ipynb` first, then `Vendor_Performance_Analysis.ipynb`.

---

## 📊 Business Questions Answered

1. Which brands need promotional or pricing adjustments?
2. Which vendors contribute the most to total purchases?
3. What is the impact of bulk purchasing on unit costs?
4. Which vendors and brands have the strongest sales performance?
5. How does stock turnover relate to profitability?

---

## 🙋 Author

**Mohd Arshad Khan**
[LinkedIn](www.linkedin.com/in/mohd-arshad-khan-470921264) • [GitHub](https://github.com/MohdArshadKhan30)
