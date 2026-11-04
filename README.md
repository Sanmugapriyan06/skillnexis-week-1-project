# skillnexis-week-1-project
Sales Performance Dashboard using Microsoft Excel to analyze Global Superstore 2016 data. Includes data cleaning, KPI metrics, revenue analysis, category-wise sales, yearly trends, department-wise revenue, and data visualization
# Week 1 Project: Sales Performance Dashboard (Excel)

Data Analyst Course, Week 1: Excel & Data Fundamentals

An Excel dashboard that analyzes sales performance for the **Global Superstore 2016** dataset, covering total revenue, sales by category, yearly trends and department-wise revenue.

## Deliverable

`Week1_Sales_Dashboard.xlsx`

| Sheet | Purpose |
|---|---|
| **Dashboard** | KPI tiles (Total Revenue, Total Profit, Profit Margin, Units Sold, Order Lines) and four charts |
| **Pivot Tables** | Summary tables behind the charts: total revenue, category, yearly, department and market |
| **Data** | Cleaned Orders data (51,290 rows, 2012-2015) plus an `Order Year` helper column |
| **Cleaning Log** | Every data-quality check performed and the action taken |

## Dataset

- Source: [Global Superstore 2016](https://github.com/hshariq/Global-Superstore-2016-Power-BI/raw/main/global_superstore_2016.xlsx) (`Orders` sheet)
- 51,290 order lines, 24 original columns, order dates from 2012 to 2015

## Project Requirements and Where to Find Them

| Requirement | Location |
|---|---|
| Total Revenue | Dashboard KPI tile; Pivot Tables, Table 1 |
| Sales by Category | Pivot Tables, Table 2; "Sales by Category" chart |
| Yearly Sales Trends | Pivot Tables, Table 3 (with YoY growth); "Yearly Sales Trend" chart |
| Department-wise Revenue | Pivot Tables, Table 4; "Department-wise Revenue" chart |

An extra table, Revenue by Market (Table 5), is also included.

## Key Findings

- **Total revenue:** $12,642,502, with profit of $1,467,457 (11.6% margin).
- **Categories:** Technology ($4.74M) leads, followed by Furniture ($4.11M) and Office Supplies ($3.79M).
- **Yearly trend:** Revenue grew every year, from $2.26M (2012) to $4.30M (2015). Growth was +18.5% in 2013, +27.2% in 2014 and +26.3% in 2015.
- **Departments:** Phones, Copiers, Chairs and Bookcases are the top four revenue generators.
- **Markets:** Asia Pacific is the largest market, followed by Europe and USCA.

## Data Cleaning Summary

| Check | Result |
|---|---|
| Fully duplicated rows | None |
| Duplicate Row IDs | None |
| Missing values | Only `Postal Code` (41,296 non-US rows), filled with `N/A` |
| Sales or Quantity <= 0 | None |
| Ship Date before Order Date | None |
| Stray whitespace in text fields | None |

Rows were sorted by Order Date. Details are in the **Cleaning Log** sheet.

## Method and Assumptions

- **Revenue** is the `Sales` column.
- **Department** is the product `Sub-Category` (for example Phones, Chairs, Binders), because the dataset has no separate department field.
- The summary tables are built with live `SUMIFS` formulas on the `Data` sheet in a PivotTable layout. They are not native Excel PivotTables, but they recalculate if the data changes.
- A reconciliation check on the Pivot Tables sheet confirms every breakdown adds up to total revenue (shows `OK`).

## Creating Native PivotTables (optional)

1. Open the `Data` sheet and click any cell in the table.
2. Go to **Insert > PivotTable**.
3. Use `Category`, `Sub-Category` or `Order Year` as Rows and `Sum of Sales` as Values.

The results should match the Pivot Tables sheet.

## Tools

Microsoft Excel (works in Excel 2007 or later), with formulas `SUMIFS`, `SUM`, `COUNT`, `YEAR` and `IF`.
