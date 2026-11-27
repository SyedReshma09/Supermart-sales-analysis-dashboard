# 🛍️ Supermarket Sales Analysis Dashboard (Excel)

An interactive, formula-driven **Excel dashboard** that analyses grocery item sales across supermarket outlets – covering overall performance, category and outlet comparisons, sales relationships and a full statistical analysis.

> Built for the **SapphireIQ Data Analytics Internship** project brief (*Supermarket Sales Analysis Dashboard*).

![Dashboard preview](supermarket_preview.png)

---

## 📌 Business Context

Rick, a Data Analyst Intern, is asked to help management understand sales performance across product categories and store outlets. The sales data exists only as a raw dataset, so it is hard to spot the best-performing products, compare outlets or see sales patterns. The goal is an **interactive Excel dashboard** that presents key metrics, category contributions, outlet comparisons and statistical insights.

## 🎯 Objectives & Questions Answered

| # | Objective | Questions answered on the dashboard |
|---|-----------|--------------------------------------|
| 1 | **Overall Sales Performance** | Total sales revenue · average sales per record · average item visibility |
| 2 | **Product Category & Sales Comparison** | Share of sales from the top 4 categories vs the rest · highest / lowest categories · sales by outlet type |
| 3 | **Outlet Performance & Sales Relationships** | Sales by outlet for Low Fat vs Regular · visibility vs sales relationship · category contribution by outlet type |
| 4 | **Statistical Analysis of Sales** | Mean / median / min / max · variation (std. deviation, CV) · unusual records (IQR & ±2σ) · average sales by category, outlet type and location |

---

## ✨ Key Features

- **3 interactive dropdown filters** – Outlet Type, Location Tier, Item Fat Content. Every KPI, chart, table and insight updates instantly (no macros).
- **Statistics that respond to filters** – mean, median, quartiles, standard deviation and correlation are recalculated for whatever segment you pick.
- **Unusual-value check** – IQR fences and ±2σ test, plus Top 10 highest and lowest records with Z-scores.
- **Pareto table** – category ranking with share and cumulative %, including the "Top 4 vs the rest" split.
- **Heatmap** – category contribution by outlet type (conditional formatting).
- **Auto-generated insights** – plain-English sentences written with formulas, so they change with the filters.
- **11 charts** – bars, doughnut, line, histogram.
- **52,000+ live formulas** – no hard-coded results.

---

## 📊 Dataset

| Item | Detail |
|------|--------|
| Source | BlinkIT grocery data (`Supermarket Sales Analysis Dashboard (V.2).xlsx`) |
| Records | 8,523 |
| Columns | Item Fat Content, Item Identifier, Item Type, Outlet Establishment Year, Outlet Identifier, Outlet Location Type, Outlet Size, Outlet Type, Item Visibility, Item Weight, Sales, Rating |
| Coverage | 16 item types · 10 outlets · 4 outlet types · 3 location tiers |

### Data cleaning
- **Item Fat Content** had inconsistent labels (`LF`, `low fat`, `reg`) → standardised to **Low Fat / Regular**.
- Helper columns added on the `Data` sheet: clean fat content, visibility band, filter flag, and filtered-sales columns that power the statistics.
- **Left as-is (documented):** 1,463 blank *Item Weight* values and 526 records with zero *Item Visibility* – neither affects the sales analysis.
- The dataset does not state a currency, so sales are shown as plain numbers.

---

## 🔍 Key Findings (all records)

- **Total sales: 1,201,681** across 8,523 records – **141.0 average per record** (median 143.0).
- **Average item visibility: 6.61%**; average rating **3.97 / 5**.
- **Top 4 categories** (Fruits & Vegetables, Snack Foods, Household, Frozen Foods) contribute **50.6%** of sales; the other 12 contribute 49.4%. **Seafood** is the lowest category.
- **Supermarket Type1** generates **65.5%** of sales; Type3 the least (10.9%).
- **Visibility has no relationship with sales** (correlation −0.001) – the trend is flat across visibility bands.
- **Low Fat items account for ~65%** of sales.
- Sales vary **moderately-to-highly** (std. deviation 62.3, CV 44%).
- **No statistical outliers** by the IQR rule; only **14 records (0.2%)** fall beyond ±2 standard deviations.
- Average sales are almost identical across outlet types and location tiers – differences are small.

---

## 🗂️ Workbook Structure

| Sheet | Purpose |
|-------|---------|
| **Dashboard** | One-page interactive report: filters, KPIs, charts, heatmap, tables, insights. |
| **Analysis** | Calculation layer – aggregations, rankings, statistics and insight sentences. |
| **Data** | Cleaned dataset (8,523 rows) with helper columns M–R. |

## 🧰 Excel Techniques Used

`SUMIFS` · `COUNTIFS` · `AVERAGEIFS` · `MEDIAN` · `QUARTILE` · `STDEV` · `CORREL` · `INDEX / MATCH` · `LARGE / SMALL` (dynamic ranking) · wildcard "All" filters · helper columns for filtered statistics · Data Validation dropdowns · Conditional Formatting (colour scales, data bars) · native Excel charts · formula-driven text.

---

## ▶️ How to Use

1. Download `Supermarket_Sales_Analysis_Dashboard.xlsx`.
2. Open in **Microsoft Excel** (2016 or later, desktop recommended) and go to the **Dashboard** sheet.
3. Click the blue **Outlet Type / Location Tier / Item Fat Content** boxes and pick a value.
4. Choose **All** to reset a filter.

> Charts that compare outlet types, locations or fat types ignore their own filter so every bar stays visible.

## 📁 Suggested Repository Structure

```
├── Supermarket_Sales_Analysis_Dashboard.xlsx
├── supermarket_preview.png
├── data/
│   └── Supermarket Sales Analysis Dashboard (V.2).xlsx      # raw dataset
├── docs/
│   └── Sapphire IQ Supermarket Sales Analysis(V.2).pdf      # project brief
└── README.md
```

## 📝 Definitions

- **Record** = one row of the dataset (one item at one outlet).
- **IQR rule** – outlier if below Q1 − 1.5×IQR or above Q3 + 1.5×IQR.
- **Z-score** – how many standard deviations a record is from the mean.
- **CV** – coefficient of variation = standard deviation ÷ mean.

Output Image:
<img width="1050" height="2755" alt="image" src="https://github.com/user-attachments/assets/0a579add-e53c-49b3-b49b-e7b642848fc6" />


*Project brief by SapphireIQ – Brilliant Minds. Intelligent Solutions.*
