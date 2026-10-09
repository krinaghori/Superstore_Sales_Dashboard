<div align="center">

# 🛒 SUPERSTORE SALES DASHBOARD

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=22&pause=1000&color=38BDF8&center=true&vCenter=true&width=560&lines=Filter+%7C+Explore+%7C+Visualize+%7C+Decide;Sales%2C+Profit+%26+Region+at+a+Glance;Built+in+Power+BI+%F0%9F%93%8A" alt="Typing SVG" />

<br/>

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Dataset](https://img.shields.io/badge/Dataset-Sample_Superstore-blue?style=for-the-badge)
![Records](https://img.shields.io/badge/Records-9%2C994-green?style=for-the-badge)
![Visuals](https://img.shields.io/badge/Data_Visuals-11-orange?style=for-the-badge)
![Slicers](https://img.shields.io/badge/Slicers-2-purple?style=for-the-badge)
![Pages](https://img.shields.io/badge/Pages-1-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge)

<br/>

> 🚀 A **single-page Power BI report** that turns 9,994 Superstore order lines (2014–2017) into an interactive dashboard — 4 KPI cards, 4 charts, 2 slicers, and a Ship Mode list — so sales, profit, category, region, month, and state performance can be explored in real time.

<br/>

<img src="dashboard_screenshots/dashboard_overview.png" alt="Superstore Sales Dashboard — full view" width="850"/>

</div>

---

## 📑 Table of Contents

1. [Overview](#-overview)
2. [Problem Statement](#-problem-statement)
3. [Features](#-features)
4. [Key Features](#-key-features)
5. [Report Structure](#-report-structure)
6. [Dashboard Layout](#-dashboard-layout)
7. [Data Preparation (Power Query)](#-data-preparation-power-query)
8. [Data Model & Fields](#-data-model--fields)
9. [Panel 1 — KPI Cards](#-panel-1--kpi-cards)
10. [Panel 2 — Filters](#-panel-2--filters)
11. [Panel 3 — Sales by Category](#-panel-3--sales-by-category)
12. [Panel 4 — Profit by Region](#-panel-4--profit-by-region)
13. [Panel 5 — Sales in Months](#-panel-5--sales-in-months)
14. [Panel 6 — Profit by State](#-panel-6--profit-by-state)
15. [Tech Stack](#-tech-stack)
16. [Results & Insights](#-results--insights)
17. [Advantages](#-advantages)
18. [Known Limitations](#-known-limitations)
19. [How to Open & Use](#-how-to-open--use)
20. [License](#-license)
21. [Author](#-author)
22. [Acknowledgements](#-acknowledgements)

---

## 🔭 Overview

**Superstore Sales Dashboard** is a single-page `.pbix` report built on the **Sample - Superstore** dataset — **9,994 order lines** placed between **3 Jan 2014 and 30 Dec 2017**. A dark-navy sidebar holds the filters (Category slicer, Region slicer, and a Ship_Mode list), while the main canvas shows four headline KPI cards and four charts: two bar charts, a pie chart, and a donut chart.

Every visual is **live and connected** to one data model: choosing a Region or Category instantly updates the KPI cards and charts, with no formulas to edit. All KPIs are built from Power BI's **implicit aggregations** (Sum and Average) — the report contains no custom DAX measures.

The report is built entirely with native Power BI visuals — no custom visuals and no R/Python scripts.

---

## ❗ Problem Statement

A raw table of ~10,000 order lines — with sales, profit, discount, quantity, category, region, state, and ship mode — is hard to read as rows and columns. It is difficult to answer the questions a sales manager needs answered quickly, such as:

- What are the total sales, profit, quantity, and average discount for whatever filter is applied?
- Which product category brings in the most revenue?
- Which region is the most profitable, and which one lags behind?
- In which months do sales peak?
- Which states generate the most profit — and which ones lose money?

**Superstore Sales Dashboard** answers these by combining KPI cards, bar charts, a monthly pie chart, and a state-level donut chart on **one interactive canvas**.

---

## ✨ Features

| Feature | Visual | Description |
|---|---|---|
| 💰 **Total Sales** | Card | Sum of `Sales` for the current filter |
| 📈 **Total Profit** | Card | Sum of `Profit` for the current filter |
| 📦 **Total Quantity** | Card | Sum of `Quantity` (units sold) |
| 🏷️ **Average Discount** | Card | Average of `Discount` |
| 🗂️ **Category Filter** | List Slicer | Furniture / Office Supplies / Technology |
| 🌍 **Region Filter** | List Slicer | Central / East / South / West |
| 🚚 **Ship_Mode List** | Table | First Class, Same Day, Second Class, Standard Class |
| 📊 **Sales by Category** | Clustered Bar Chart | Total sales per product category |
| 🗺️ **Profit by Region** | Clustered Bar Chart | Total profit per region |
| 📅 **Sales in Months** | Pie Chart | Sales by calendar month (Date Hierarchy → Month) |
| 🍩 **Profit by State** | Donut Chart | State-level profit share, with the net total in the center |

---

## 🌟 Key Features

| Feature | Description |
|---|---|
| 🔗 **One Connected Model** | All 11 data visuals read from a single table, so filters apply consistently across the page |
| 🧮 **Implicit Aggregations Only** | Cards and charts use Sum / Average over columns — no hardcoded numbers and no custom DAX |
| 📅 **Auto Date Hierarchy** | The monthly pie chart is built on Power BI's automatic Date Hierarchy at the **Month** level |
| 🧪 **Documented Data Prep** | A 10-step Power Query pipeline cleans types, renames columns, and splits `Order_ID` |
| 🎨 **Branded Design** | Navy sidebar, Fluent 2 base theme plus a custom theme, and a faint background watermark |
| 🖼️ **Fit-to-Page Canvas** | Designed at 1920 × 1080 with *Fit to page*, so it scales across screen sizes |
| ♻️ **Native Visuals Only** | Card, Clustered Bar, Pie, Donut, Table, and List Slicer |

---

## 📁 Report Structure

```
📦 Superstore_Sales_Dashboard.pbix
 ┣ 📄 Data Model            ← 1 data table: "Sample - Superstore" (9,994 rows × 20 columns)
 ┃                            + auto-generated date tables for Order_Date and Ship_Date
 ┣ 📄 Report (1 page)       ← "Dashboard" (1920 × 1080)
 ┃ ┣ 🧭 Sidebar              → Title + Category slicer + Region slicer + Ship_Mode table
 ┃ ┣ 📊 KPI Row              → Total Sales · Total Profit · Total Quantity · Average Discount
 ┃ ┣ 📊 Chart Row 1          → Sales by Category (bar) · Profit by Region (bar)
 ┃ ┗ 📊 Chart Row 2          → Sales in Months (pie) · Profit by State (donut)
 ┣ 🖼️ dashboard_screenshots/  ← Dashboard preview image
 ┗ 📄 README.md              ← Project documentation (you're here!)
```

> Open the `.pbix` in Power BI Desktop — every visual recalculates as filters change.

---

## 🖥️ Dashboard Layout

```
┌──────────────────────┬─────────────────────────────────────────────────────┐
│   SUPERSTORE SALES   │┌────────────┬────────────┬────────────┬────────────┐│
│                      ││Total Sales │Total Profit│ Total Qty  │Avg Discount││
│ Category (slicer)    │└────────────┴────────────┴────────────┴────────────┘│
│ o Furniture          │┌─────────────────────────┬─────────────────────────┐│
│ o Office Supplies    ││ Sales by Category       │ Profit by Region        ││
│ o Technology         ││ (clustered bar)         │ (clustered bar)         ││
│                      ││                         │                         ││
│ Region (slicer)      ││                         │                         ││
│ o Central            │└─────────────────────────┴─────────────────────────┘│
│ o East               │┌─────────────────────────┬─────────────────────────┐│
│ o South              ││ Sales in Months         │ Profit by State         ││
│ o West               ││ (pie, by month)         │ (donut, with total)     ││
│                      ││                         │                         ││
│ Ship_Mode (table)    ││                         │                         ││
│ First Class          │└─────────────────────────┴─────────────────────────┘│
│ Same Day             │                                                     │
│ Second Class         │                                                     │
│ Standard Class       │                                                     │
└──────────────────────┴─────────────────────────────────────────────────────┘
```

---

## 🧪 Data Preparation (Power Query)

The `Sample - Superstore` table is loaded from a CSV file and cleaned with the following Power Query (M) steps:

| # | Step | What it does |
|---|---|---|
| 1 | **Load CSV** | Reads `Sample - Superstore.csv` (comma-delimited, 21 columns) |
| 2 | **Promote headers** | Uses the first row as column names |
| 3 | **Set data types** | Whole numbers, text, dates, and decimal numbers assigned to every column |
| 4 | **Remove column** | Drops `Row ID` |
| 5 | **Re-type numeric columns** | `Quantity` → whole number; `Sales`, `Profit` → currency; `Discount` set back to a decimal number |
| 6 | **Rename columns** | Spaces and hyphens become underscores (`Order_Date`, `Ship_Date`, `Ship_Mode`, `Customer_ID`, `Customer_Name`, `Product_ID`, `Sub_Category`, …) |
| 7 | **Remove columns** | Drops `Country` and `Postal_Code` |
| 8 | **Replace value** | In `Segment`, **"Home Office" → "Consumer"** (leaving two segments: Consumer and Corporate) |
| 9 | **Split `Order_ID`** | Splits on `-` into `Order_ID.1` (prefix: CA / US), `Order_ID.2` (year), `Order_ID.3` (number) |
| 10 | **Final types** | `Order_ID.1` → text; `Order_ID.2` and `Order_ID.3` → whole number |

---

## 📋 Data Model & Fields

**Dataset at a glance**

| Metric | Value |
|---|---|
| Rows (order lines) | **9,994** |
| Columns | **20** |
| Order date range | **3 Jan 2014 → 30 Dec 2017** (4 years) |
| Customers · Products · Cities | 793 · 1,862 · 531 |
| States · Sub-categories | 49 · 17 |
| Segments | Consumer (6,974) · Corporate (3,020) |

**Fields used on the dashboard**

| Field | Used In |
|---|---|
| `Sales` | Total Sales card · Sales by Category · Sales in Months |
| `Profit` | Total Profit card · Profit by Region · Profit by State |
| `Quantity` | Total Quantity card |
| `Discount` | Average Discount card |
| `Category` | Category slicer · Sales by Category |
| `Region` | Region slicer · Profit by Region |
| `State` | Profit by State |
| `Order_Date` | Sales in Months (Date Hierarchy → Month) |
| `Ship_Mode` | Ship_Mode table |

**Fields available but not used on the page** — `Ship_Date`, `Order_ID.1/.2/.3`, `Customer_ID`, `Customer_Name`, `Segment`, `City`, `Product_ID`, `Sub_Category`, `Product Name`. These are ready for extra pages or drill-throughs.

---

## 💰 Panel 1 — KPI Cards

> Four native **Card** visuals, each showing one aggregated field.

| Card | Field | Aggregation | Shown on dashboard | Exact value |
|---|---|---|---|---|
| 💰 Total Sales | `Sales` | Sum | **₹2.3M** | ₹2,297,200.86 |
| 📈 Total Profit | `Profit` | Sum | **₹286.4K** | ₹286,397.02 |
| 📦 Total Quantity | `Quantity` | Sum | **38K** | 37,873 units |
| 🏷️ Average Discount | `Discount` | Average | **0.16** | 0.1562 (15.62%) |

> ✅ **Reading it:** profit is **12.47%** of sales (₹286,397.02 ÷ ₹2,297,200.86), and the average order-line discount is **15.6%**.

---

## 🎛️ Panel 2 — Filters

> Two **List Slicers** and one **Table**, all in the left sidebar.

| Control | Type | Field | Values |
|---|---|---|---|
| 🗂️ **Category** | List Slicer | `Category` | Furniture, Office Supplies, Technology |
| 🌍 **Region** | List Slicer | `Region` | Central, East, South, West |
| 🚚 **Ship_Mode** | Table | `Ship_Mode` | First Class, Same Day, Second Class, Standard Class |

---

## 📊 Panel 3 — Sales by Category

> A **Clustered Bar Chart** of total sales per category (subtitle on the chart: *"Total Sales of Category"*).

| Field Role | Field |
|---|---|
| Axis | `Category` |
| Values | Sum of `Sales` |

| Category | Total Sales | Shown on chart | Share |
|---|---|---|---|
| Technology | ₹836,154.03 | ₹0.84M | 36.40% |
| Furniture | ₹741,999.80 | ₹0.74M | 32.30% |
| Office Supplies | ₹719,047.03 | ₹0.72M | 31.30% |

> ✅ **Reading it:** Technology leads, but the three categories are close — each contributes between **31% and 36%** of sales.

---

## 🗺️ Panel 4 — Profit by Region

> A **Clustered Bar Chart** of total profit per region.

| Field Role | Field |
|---|---|
| Axis | `Region` |
| Values | Sum of `Profit` |

| Region | Total Profit | Share of Profit |
|---|---|---|
| West | ₹108,418.45 | 37.86% |
| East | ₹91,522.78 | 31.96% |
| South | ₹46,749.43 | 16.32% |
| Central | ₹39,706.36 | 13.86% |

> ✅ **Reading it:** **West and East together produce 69.8%** of all profit. West earns about **2.7×** as much as Central, the weakest region.

---

## 📅 Panel 5 — Sales in Months

> A **Pie Chart** built on the automatic **Date Hierarchy** of `Order_Date`, at the **Month** level.
>
> ℹ️ The chart adds up the **same calendar month across all four years (2014–2017)**, so it shows overall seasonality, not a single year.

| Field Role | Field |
|---|---|
| Category | `Order_Date` → Date Hierarchy → **Month** |
| Values | Sum of `Sales` |

| Month | Sales | Shown on chart | Share |
|---|---|---|---|
| January | ₹94,924.84 | ₹94.92K | 4.13% |
| February | ₹59,751.25 | *(label not displayed — slice too small)* | 2.60% |
| March | ₹205,005.49 | ₹205.01K | 8.92% |
| April | ₹137,762.13 | ₹137.76K | 6.00% |
| May | ₹155,028.81 | ₹155.0K | 6.75% |
| June | ₹152,718.68 | ₹152.72K | 6.65% |
| July | ₹147,238.10 | ₹147.24K | 6.41% |
| August | ₹159,044.06 | ₹159.04K | 6.92% |
| September | ₹307,649.95 | ₹307.65K | 13.39% |
| October | ₹200,322.98 | ₹200.32K | 8.72% |
| November | ₹352,461.07 | ₹352.46K | 15.34% |
| December | ₹325,293.50 | ₹325.29K | 14.16% |

> ✅ **Reading it:** **November, December, and September** are the three biggest months and together account for **42.9%** of sales. **January and February** are the weakest, at just **6.7%** combined.

---

## 🍩 Panel 6 — Profit by State

> A **Donut Chart** with the **net** total profit (**₹286.39K**) shown in the center.

| Field Role | Field |
|---|---|
| Category | `State` |
| Values | Sum of `Profit` |

| Rank | State | Profit | Donut share |
|---|---|---|---|
| 1 | California | ₹76,381.39 | 19.86% |
| 2 | New York | ₹74,038.55 | 19.25% |
| 3 | Washington | ₹33,402.65 | 8.68% |
| 4 | Michigan | ₹24,463.19 | 6.36% |
| 5 | Virginia | ₹18,597.95 | 4.84% |
| 6 | Indiana | ₹18,382.94 | 4.78% |
| 7 | Georgia | ₹16,250.04 | 4.22% |
| 8 | Kentucky | ₹11,199.70 | 2.91% |
| 9 | Minnesota | ₹10,823.19 | 2.81% |
| 10 | Delaware | ₹9,977.37 | 2.59% |

> ℹ️ **How to read the percentages:** a donut chart cannot draw negative values, so the shares above are calculated over the **39 profitable states only** (₹384,643.76). The center total of ₹286.39K is the **net** profit across all **49 states**.

**States that lose money (hidden from the donut):** 10 states have negative profit, totalling **−₹98,246.74**. The five largest losses are Texas (−₹25,729.36), Ohio (−₹16,971.38), Pennsylvania (−₹15,559.96), Illinois (−₹12,607.89), and North Carolina (−₹7,490.91).

> ✅ **Reading it:** **California and New York** together earn **₹150,419.94 — 52.5% of net profit** — while 10 states drag the total down.

---

## 🛠 Tech Stack

| Technology | Purpose |
|---|---|
| 📊 **Power BI Desktop** | Report authoring, data modeling, and visual design |
| 🧪 **Power Query (M)** | Loading and cleaning the CSV source |
| 🧮 **Power BI Data Model** | One data table plus auto-generated date tables |
| 📅 **Auto Date/Time Hierarchy** | Year → Quarter → Month → Day drilldown behind the monthly pie chart |
| 🎨 **Native Visuals** | Card, Clustered Bar Chart, Pie Chart, Donut Chart, Table, List Slicer |
| 🖼️ **Themes** | Fluent 2 base theme plus a custom theme file, with a background watermark image |

---

## 📊 Results & Insights

| Panel | Key Insight |
|---|---|
| 💰 **KPI Cards** | ₹2.30M sales → ₹286.4K profit (**12.47%** margin), 37,873 units, 15.6% average discount |
| 📊 **Sales by Category** | Technology leads at **36.4%**; the category mix is fairly balanced (31%–36% each) |
| 🗺️ **Profit by Region** | **West + East = 69.8%** of profit; **Central** is the weakest at 13.9% |
| 📅 **Sales in Months** | **Sep + Nov + Dec = 42.9%** of sales — strong year-end seasonality; Jan + Feb only 6.7% |
| 🍩 **Profit by State** | **California + New York = 52.5%** of net profit; **10 states** are loss-making, led by **Texas** (−₹25.7K) |

---

## 💡 Advantages

- **Fully Interactive** — every card and chart responds to the slicers, with no static exports
- **Compact but Complete** — one page covers sales, profit, time, geography, and category
- **Well-Known Dataset** — built on Sample - Superstore, so it is easy to recreate or extend
- **Transparent Data Prep** — all cleaning is done in Power Query and documented step by step
- **Simple, Maintainable Logic** — implicit aggregations only, so there is no DAX to debug
- **Native Visuals Only** — opens cleanly in any standard Power BI Desktop install
- **Room to Grow** — 11 fields (Customer, Segment, City, Sub_Category, Ship_Date, …) are loaded but unused, ready for new pages

---

## ⚠️ Known Limitations

- The report has **one page** — there is no drill-through page for a state, customer, or product
- **Ship_Mode** is built as a **Table** visual, not a slicer, so it works as a list rather than a dedicated filter control like the Category and Region slicers
- The **Sales in Months** pie combines the same month from **all four years (2014–2017)**; there is no Year slicer or year-by-year trend
- The **Profit by State** donut shows shares of **profitable states only**, so the **10 loss-making states** (−₹98,246.74 combined) do not appear on it
- **Average Discount** is a simple average of the row-level `Discount`, not weighted by sales
- The data source is a **local file path** on the original author's `D:` drive, so refreshing the report on another computer requires updating the path (see *How to Open & Use*)
- In Power Query, the `Segment` value **"Home Office" is replaced with "Consumer"**, so the original three-segment split is not preserved
- Values are formatted with **₹**, while the dataset itself covers **U.S. states** — confirm the intended currency before presenting
- The report is **descriptive only** — there is no forecast or trend line
- Editing the `.pbix` requires **Power BI Desktop** (Windows)

---

## ▶️ How to Open & Use

1. Install **Power BI Desktop** (free, Windows).
2. Open `Superstore_Sales_Dashboard.pbix`. The data is already stored in the file, so the visuals load immediately.
3. Click items in the **Category** and **Region** slicers to filter every visual; click a chart segment to cross-filter the rest of the page.
4. **To refresh the data on another computer:** go to *Home → Transform data ▾ → Data source settings → Change Source…* and point it to your own copy of `Sample - Superstore.csv`, then click **Refresh**.

---

## 📄 License

```
MIT License

Copyright (c) 2026

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND.
```

---

## 👩‍💻 Author

<div align="center">

| | |
|---|---|
| 👤 **Name** | _KRINA GHORI_ |
| 📊 **Tool** | Power BI Desktop |
| 📁 **Project** | Superstore Sales Dashboard |
| 💡 **Purpose** | Interactive sales, profit & regional analytics dashboard |

<br/>

Made with 💙 using **Power BI**

![Power BI Love](https://img.shields.io/badge/Made%20with-%F0%9F%92%99%20Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)

</div>

---

## 🙏 Acknowledgements

- 📊 **Microsoft Power BI Team** — for the report engine and visualization framework behind this dashboard
- 📖 **Sample - Superstore Dataset** — the widely used demo dataset behind this report
- 📖 **Power BI Documentation** — for reference on Power Query, Date Hierarchies, Cards, and native chart visuals
- 💻 **Open Source Community** — for README badge tools (shields.io) and typing SVG animations
- 🎓 **All learners** — who build dashboards like this to sharpen their BI fundamentals

---

<div align="center">

⭐ **Star this repo if you found it helpful!** ⭐

</div>
