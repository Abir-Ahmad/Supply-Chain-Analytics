# Supply Chain & Delivery Performance Analysis

## Overview

Analysis of the **Olist Brazilian E-Commerce Public Dataset** to investigate delivery punctuality, customer satisfaction, and freight costs. The project combines **Excel**, **SQLite/SQL**, and **Power BI** to explore operational performance and present findings in an interactive dashboard.

## Tools

- **Excel:** data exploration, calculated fields, PivotTables
- **SQLite / DB Browser for SQLite:** joins, common table expressions (CTEs), aggregation, category-level analysis
- **Power BI:** Power Query transformations, relational data model, DAX calculations, dashboard visuals

## Key findings

### Delivery performance

- **99,441** orders in the dataset.
- **96,476** orders had confirmed delivery dates and were included in the punctuality analysis.
- **88,655 (91.89%)** were delivered on time or early; **7,821 (8.11%)** arrived after their estimated delivery dates.

### Delivery delays and customer reviews

| Delivery category | Average review score (out of 5) |
|---|---:|
| On time / early | 4.29 |
| 1–3 days late | 3.77 |
| 4–7 days late | 2.32 |
| 8+ days late | 1.73 |

Across all late deliveries, the average review score was **2.57/5**, compared with **4.29/5** for on-time or early deliveries. Longer delays were associated with lower customer satisfaction; this is an observational relationship, not proof of causation.

### Freight costs

- Analysed **112,650** order-item records.
- Freight burden was calculated as `freight_value / (price + freight_value)` for each item.
- **21.69%** of items had freight burden greater than **30%**.
- Among higher-volume product categories, **electronics** had an average freight burden of approximately **35.81%**, while **telephony** was approximately **30%**.

## Dashboard

The Power BI report includes four KPI cards—total orders, on-time delivery rate, average customer review score, and high-freight item rate—and four visuals covering delivery status, review scores by delivery status, review scores by delay severity, and average freight burden by product category.

![Power BI dashboard overview](screenshots/dashboard_overview.png)

**View the dashboard:** The screenshot above previews the report. Download `supply_chain_dashboard.pbix` and open it in Power BI Desktop to explore the interactive visuals.

## Project files

```text
README.md
screenshots/
    dashboard_overview.png
sql/
    category_freight_analysis.sql
    category_delivery_analysis.sql
    delivery_review_analysis.sql
supply_chain_analysis.xlsx
supply_chain_dashboard.pbix
```

The raw source CSVs and working SQLite database are excluded from this repository; the original dataset is available from the source below.

## Data source

**[Olist Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)** (Kaggle). The analysis uses order, order-item, review, product, and product-category translation data.

## Takeaway

Delivery punctuality is strongly associated with customer review scores, with progressively worse ratings for longer delays. Freight burden also differs across product categories, suggesting opportunities for further investigation into logistics costs and customer experience.
