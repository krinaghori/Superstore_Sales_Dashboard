<div align="center">

# 🛒 SUPERSTORE SALES DASHBOARD

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=22&pause=1000&color=38BDF8&center=true&vCenter=true&width=560&lines=Filter+%7C+Explore+%7C+Visualize+%7C+Decide;Sales%2C+Profit+%26+Region+at+a+Glance;Built+in+Power+BI+%F0%9F%93%8A" alt="Typing SVG" />

<br/>

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Dataset](https://img.shields.io/badge/Dataset-Sample_Superstore-blue?style=for-the-badge)
![Visuals](https://img.shields.io/badge/Data_Visuals-11-orange?style=for-the-badge)
![Slicers](https://img.shields.io/badge/Slicers-2-purple?style=for-the-badge)
![Page](https://img.shields.io/badge/Pages-1-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge)

<br/>

> 🚀 A **single-page Power BI report** that turns the classic Superstore sales dataset into an interactive dashboard — 4 KPI cards, 4 charts, 2 slicers, and a Ship Mode list — so Sales, Category, Region, and State performance can all be sliced in real time.

</div>

---

## 📑 Table of Contents

1. [Overview](#-overview)
2. [Problem Statement](#-problem-statement)
3. [Features](#-features)
4. [Key Features](#-key-features)
5. [Report Structure](#-report-structure)
6. [Dashboard Layout](#-dashboard-layout)
7. [Expected Dataset Format](#-expected-dataset-format)
8. [Panel 1 — KPI Cards](#1️⃣-panel-1--kpi-cards)
9. [Panel 2 — Filters](#2️⃣-panel-2--filters)
10. [Panel 3 — Sales by Category](#3️⃣-panel-3--sales-by-category)
11. [Panel 4 — Profit by Region](#4️⃣-panel-4--profit-by-region)
12. [Panel 5 — Sales in Months](#5️⃣-panel-5--sales-in-months)
13. [Panel 6 — Profit by State](#6️⃣-panel-6--profit-by-state)
14. [Tech Stack](#-tech-stack)
15. [Results & Insights](#-results--insights)
16. [Advantages](#-advantages)
17. [Known Limitations](#-known-limitations)
18. [License](#-license)
19. [Author](#-author)
20. [Acknowledgements](#-acknowledgements)

---

## 🔭 Overview

**Superstore Sales Dashboard** is a single-page `.pbix` report built on the **Sample - Superstore** table. A dark-navy sidebar hosts the filters (Category, Region, and a Ship_Mode list), while the main canvas shows four headline KPI cards and four charts — two bar charts, a pie chart, and a donut chart — all cross-filtering together whenever a slicer or chart segment is clicked.

Instead of static exported charts, every visual is **live and connected**: picking a Region instantly updates the KPI cards, the Category bar chart, the monthly sales pie, and the State-level profit donut, without touching a single formula.

Built entirely in Power BI Desktop with native visuals — no custom visuals, no R/Python scripts.

---

## ❗ Problem Statement

A raw table of superstore transactions — sales, profit, discount, quantity, category, region, and ship mode — is hard to read as rows and columns. It's difficult to answer the questions a sales manager needs answered *in the moment*, such as:

- What are the total sales, profit, quantity, and average discount for whatever filter is applied?
- Which product category brings in the most revenue?
- Which region is the most profitable, and which lags behind?
- How does sales volume move month to month?
- Which states contribute the most profit?

**Superstore Sales Dashboard** answers these by combining KPI cards, categorical bar charts, a monthly pie chart, and a state-level donut chart into **one interactive canvas**.

---

## ✨ Features

| Feature | Visual | Description |
|---|---|---|
| 💰 **Total Sales** | Card | Sum of `Sales` across the filtered data |
| 📈 **Total Profit** | Card | Sum of `Profit` across the filtered data |
| 📦 **Total Quantity** | Card | Sum of `Quantity` (units sold) |
| 🏷️ **Average Discount** | Card | Average of `Discount` |
| 🗂️ **Category Filter** | List Slicer | Furniture / Office Supplies / Technology |
| 🌍 **Region Filter** | List Slicer | Central / East / South / West |
| 🚚 **Ship_Mode List** | Table | Lists First Class, Same Day, Second Class, Standard Class |
| 📊 **Sales by Category** | Clustered Bar Chart | Total sales per product category |
| 📊 **Profit by Region** | Clustered Bar Chart | Total profit per region |
| 🥧 **Sales in Months** | Pie Chart | Monthly share of sales via the Order Date hierarchy |
| 🍩 **Profit by State** | Donut Chart | State-level profit share with total in the center |

---

## 🌟 Key Features

| Feature | Description |
|---|---|
| 🔗 **Interactive Cross-Filtering** | Clicking a slicer or chart segment filters the other visuals on the page |
| 🧮 **Live Aggregations** | Cards and charts use native Sum / Average aggregations over the data model — no hardcoded numbers |
| 📅 **Date Hierarchy** | The monthly pie chart uses Power BI's automatic Date Hierarchy at the **Month** level |
| 🎨 **Branded Sidebar** | A navy sidebar with a title card keeps filters visually separate from the analysis area |
| 🖼️ **Fit-to-Page Canvas** | Designed at 1920×1080 with `FitToPage`, so it scales across screen sizes |
| ♻️ **Native Visuals Only** | Card, Clustered Bar, Pie, Donut, Table, and List Slicer — nothing from the marketplace |

---

## 📁 Report Structure

```
📦 Superstore_Sales_Dashboard.pbix
 ┣ 📄 Data Model          ← "Sample - Superstore" table
 ┃                          (Sales, Profit, Discount, Quantity, Category, Region, State,
 ┃                           Ship_Mode, Order_Date)
 ┣ 📄 Report (1 page)     ← "Dashboard"
 ┃ ┣ 🧭 Sidebar            → Title + Category slicer + Region slicer + Ship_Mode list
 ┃ ┣ 📊 KPI Row            → Total Sales · Total Profit · Total Quantity · Average Discount
 ┃ ┣ 📊 Chart Row 1        → Sales by Category (bar) · Profit by Region (bar)
 ┃ ┗ 📊 Chart Row 2        → Sales in Months (pie) · Profit by State (donut)
 ┣ 🖼️ dashboard_screenshots/ ← Dashboard preview image
 ┗ 📄 README.md            ← Project documentation (you're here!)
```

> Open the `.pbix` in Power BI Desktop; every visual recalculates as filters change.

---

## 🖥️ Dashboard Layout

```
┌──────────────────────┬──────────────────────────────────────────────────┐
│  🧭 SIDEBAR           │  💰 Total Sales │ 📈 Total Profit │ 📦 Qty │ 🏷️ Disc │
│                       ├───────────────────────────┬──────────────────────┤
│  🗂️ Category          │  📊 Sales by Category      │  📊 Profit by Region   │
│    • Furniture        │     (Clustered Bar)        │     (Clustered Bar)    │
│    • Office Supplies  ├───────────────────────────┼──────────────────────┤
│    • Technology       │  🥧 Sales in Months        │  🍩 Profit by State    │
│                       │     (Pie Chart)            │     (Donut Chart)      │
│  🌍 Region            │                            │                        │
│    • Central / East   │                            │                        │
│    • South / West     │                            │                        │
│                       │                            │                        │
│  🚚 Ship_Mode         │                            │                        │
│    • First Class      │                            │                        │
│    • Same Day         │                            │                        │
│    • Second Class     │                            │                        │
│    • Standard Class   │                            │                        │
└──────────────────────┴───────────────────────────┴──────────────────────┘
```

<div align="center">
<img src="dashboard_screenshots/dashboard_overview.png" alt="Superstore Sales Dashboard — full view" width="800"/>
</div>

---

## 📋 Expected Dataset Format

The report reads from a single table, **Sample - Superstore**, using these fields:

| Field | Used In |
|---|---|
| `Order_Date` | Sales in Months (Date Hierarchy → Month) |
| `Category` | Category slicer · Sales by Category |
| `Region` | Region slicer · Profit by Region |
| `State` | Profit by State |
| `Ship_Mode` | Ship_Mode list |
| `Sales` | Total Sales card · Sales by Category · Sales in Months |
| `Profit` | Total Profit card · Profit by Region · Profit by State |
| `Discount` | Average Discount card |
| `Quantity` | Total Quantity card |

---

## 1️⃣ Panel 1 — KPI Cards

> Four native **Card** visuals, each showing one aggregated field.

| Card | Field | Aggregation | Value |
|---|---|---|---|
| 💰 Total Sales | `Sales` | Sum | **₹2.3M** |
| 📈 Total Profit | `Profit` | Sum | **₹286.4K** |
| 📦 Total Quantity | `Quantity` | Sum | **38K** |
| 🏷️ Average Discount | `Discount` | Average | **0.16** |

> ✅ **Reading it:** about **12.5%** of sales turns into profit (₹286.4K ÷ ₹2.3M), with an average discount of 16%.

---

## 2️⃣ Panel 2 — Filters

> Two **List Slicers** and one **Table**, all in the left sidebar.

| Control | Type | Values |
|---|---|---|
| 🗂️ **Category** | List Slicer | Furniture, Office Supplies, Technology |
| 🌍 **Region** | List Slicer | Central, East, South, West |
| 🚚 **Ship_Mode** | Table | First Class, Same Day, Second Class, Standard Class |

---

## 3️⃣ Panel 3 — Sales by Category

> A **Clustered Bar Chart** of total sales per category.

| Field Role | Field |
|---|---|
| Axis | `Category` |
| Values | Sum of `Sales` |

| Category | Total Sales |
|---|---|
| Technology | ₹0.84M |
| Furniture | ₹0.74M |
| Office Supplies | ₹0.72M |

> ✅ **Reading it:** Technology leads, but all three categories sit within ₹0.72M–₹0.84M — no single category dominates.

---

## 4️⃣ Panel 4 — Profit by Region

> A **Clustered Bar Chart** of total profit per region.

| Field Role | Field |
|---|---|
| Axis | `Region` |
| Values | Sum of `Profit` |

| Region | Profit *(approx., read from chart axis)* |
|---|---|
| West | ~₹108K |
| East | ~₹91K |
| South | ~₹47K |
| Central | ~₹40K |

> ✅ **Reading it:** **West** and **East** together produce roughly 70% of total profit, while **Central** trails far behind.

---

## 5️⃣ Panel 5 — Sales in Months

> A **Pie Chart** built on the Date Hierarchy at the **Month** level.

| Field Role | Field |
|---|---|
| Category | `Order_Date` → Date Hierarchy → **Month** |
| Values | Sum of `Sales` |

| Month | Sales | Share |
|---|---|---|
| January | ₹94.92K | 4.13% |
| February | *(smallest slice, label hidden)* | — |
| March | ₹205.01K | 8.92% |
| April | ₹137.76K | 6.00% |
| May | ₹155.0K | 6.75% |
| June | ₹152.72K | 6.65% |
| July | ₹147.24K | 6.41% |
| August | ₹159.04K | 6.92% |
| September | ₹307.65K | 13.39% |
| October | ₹200.32K | 8.72% |
| November | ₹352.46K | 15.34% |
| December | ₹325.29K | 14.16% |

> ✅ **Reading it:** **November, December, and September** are the three biggest months and together make up about **43%** of sales, while **February** and **January** are the weakest.

---

## 6️⃣ Panel 6 — Profit by State

> A **Donut Chart** with the total profit (**₹286.39K**) shown in the center.

| Field Role | Field |
|---|---|
| Category | `State` |
| Values | Sum of `Profit` |

| State | Profit | Share |
|---|---|---|
| California | ₹76.38K | 19.86% |
| New York | ₹74.04K | 19.25% |
| Washington | ₹33.4K | 8.68% |
| Michigan | ₹24.46K | 6.36% |
| Virginia | ₹18.6K | 4.84% |
| Indiana | ₹18.38K | 4.78% |
| Georgia | ₹16.25K | 4.22% |
| Kentucky | ₹11.2K | 2.91% |
| Minnesota | ₹10.8K | 2.81% |
| Delaware | ₹9.98K | 2.59% |
| New Jersey | ₹9.77K | 2.54% |
| Wisconsin | ₹8.4K | 2.18% |
| Rhode Island | ₹7.29K | 1.89% |
| *(remaining states)* | smaller slivers | — |

> ✅ **Reading it:** **California** and **New York** are the two profit leaders by a wide margin — each contributes about a fifth of the donut — followed by a long tail of states in the low single digits.
>
> ℹ️ State names are matched to slices using the legend order (largest to smallest) and the labels shown in the screenshot.

---

## 🛠 Tech Stack

| Technology | Purpose |
|---|---|
| 📊 **Power BI Desktop** | Report authoring, data modeling, and visual design |
| 🧮 **Power BI Data Model** | Holds the `Sample - Superstore` table |
| 📅 **Date Hierarchy** | Year → Quarter → Month drilldown behind the monthly pie chart |
| 🎨 **Native Visuals** | Card, Clustered Bar Chart, Pie Chart, Donut Chart, Table, List Slicer |
| 🖼️ **Report Theme** | Fluent 2 base theme with a custom navy sidebar and background watermark |

---

## 📊 Results & Insights

| Panel | Key Insight |
|---|---|
| 💰 **KPI Cards** | ₹2.3M sales → ₹286.4K profit (~12.5% margin), 38K units, 16% average discount |
| 📊 **Sales by Category** | Technology narrowly leads (₹0.84M); the category mix is well balanced |
| 📊 **Profit by Region** | **West** and **East** drive most profit; **Central** is the weakest region |
| 🥧 **Sales in Months** | **September, November, and December** carry ~43% of sales — strong year-end seasonality |
| 🍩 **Profit by State** | **California** and **New York** together contribute ~39% of the donut |

---

## 💡 Advantages

- **Fully Interactive** — every card and chart cross-filters live; no manual refresh of static charts
- **Compact but Complete** — one page covers sales, profit, time, geography, and category
- **Well-Known Dataset** — built on Sample - Superstore, so it's easy to recreate or extend
- **Native Visuals Only** — opens cleanly in any standard Power BI install
- **Clean, Presentation-Ready Design** — branded sidebar and consistent blue palette
- **Easy to Extend** — new measures, pages, or drill-throughs can be added on top of the same model

---

## ⚠️ Known Limitations

- The report is a **single page** — there is no drill-through page for a state, category, or customer
- **Ship_Mode** is a plain **Table** visual, not a slicer, so clicking it is not set up as a dedicated filter like the Category and Region slicers
- The monthly pie chart uses Power BI's automatic **Date Hierarchy**; switching to a proper Date table would require rebuilding that visual
- Small states in the donut chart are tiny slivers — hover tooltips are needed to read them precisely
- Profit-by-Region values in this README are approximate, read from the chart's axis rather than exact labels
- The report is **descriptive only** — there is no trend line or forecast
- Editing the `.pbix` requires **Power BI Desktop** (Windows)

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
- 📖 **Power BI Documentation** — for reference on Date Hierarchies, Cards, and native chart visuals
- 💻 **Open Source Community** — for README badge tools (shields.io) and typing SVG animations
- 🎓 **All learners** — who build dashboards like this to sharpen their BI fundamentals

---

<div align="center">

⭐ **Star this repo if you found it helpful!** ⭐

</div>
