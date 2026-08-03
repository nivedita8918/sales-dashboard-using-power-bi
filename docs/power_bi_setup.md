# Power BI Setup Guide

1. Open Power BI Desktop and select **Get data** → **Text/CSV**.
2. Select `data/superstore_sales_500.csv`.
3. In Power Query, set `Order Date` and `Ship Date` to **Date**; set `Sales` and `Profit` to **Fixed decimal number**; and set `Quantity` to **Whole number**.
4. Select **Close & Apply**.
5. Create the measures below and use them on an Executive Summary page.

## Recommended measures

```DAX
Total Sales = SUM('superstore_sales_500'[Sales])

Total Profit = SUM('superstore_sales_500'[Profit])

Total Quantity = SUM('superstore_sales_500'[Quantity])

Profit Margin = DIVIDE([Total Profit], [Total Sales])

Average Order Value = DIVIDE([Total Sales], DISTINCTCOUNT('superstore_sales_500'[Order ID]))
```

## Suggested visuals

- Cards: Total Sales, Total Profit, Profit Margin, and Total Quantity
- Line chart: Total Sales by Order Date
- Bar chart: Total Sales by Category
- Bar chart: Total Profit by Region
- Treemap: Total Sales by Sub-Category
- Slicers: Region, Segment, Category, and Order Date
