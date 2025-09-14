# **Sales Performance Dashboard - Power BI**

## **Project Overview**

This project presents an interactive Power BI dashboard that provides a complete analysis of sales data for a one-week period (April 1 – April 7, 2025).
The dashboard tracks key performance indicators (KPIs), sales trends, product performance, category and region breakdowns, and payment method distributions.

## Key Features

- **KPI Overview**: 
  - Total Sales
  - Total Orders
  - Average Order Value
  - Total Items Sold
- **Sales Trend**: Daily sales analysis over the selected period.
- **Sales by Category**: Distribution of sales across product categories.
- **Sales by Region**: Regional comparison of sales performance.
- **Payment Methods**: Breakdown of transactions by payment type (Credit Card, PayPal, Debit Card).
- **Product Performance Table**: Sales, quantity sold, and average discount per product.
- **Growth Indicators**: % increase in sales, orders, and items sold.

## Project Structure

| File | Description |
|:----|:----|
| `sales1.pbix` | Power BI Dashboard file (Main project file) |
| `sales.csv.xlsx` | Source dataset containing sales transactions |

## Tools & Technologies

- **Power BI Desktop**
- **DAX (Data Analysis Expressions)** for custom calculations
- **Excel (.xlsx)** for the dataset

## DAX Measures Used

```DAX
// KPI Metrics
Total Sales = SUM('Sales'[Sales])

Orders = DISTINCTCOUNT('Sales'[Order ID])

Avg Order Value = DIVIDE([Total Sales], [Orders])

Items Sold = SUM('Sales'[Quantity])

// Trend Analysis
Sales Last Period = CALCULATE([Total Sales], DATEADD('Sales'[Order Date], -1, DAY))

Sales Growth % = DIVIDE([Total Sales] - [Sales Last Period], [Sales Last Period])

// Data Cleaning
Category Name = IF(ISBLANK('Sales'[Category]), "Undefined", 'Sales'[Category])

// Discount Analysis
Avg Discount = AVERAGE('Sales'[Discount])
```

## Dashboard Layout

1. **Top Section**:
   - KPI Cards (Total Sales, Orders, Avg. Order Value, Items Sold)
2. **Middle Section**:
   - Sales Trend Line Chart
   - Pie Chart (Sales by Category)
   - Bar Chart (Sales by Region)
   - Donut Chart (Payment Methods)
3. **Bottom Section**:
   - Product Performance Table (Product, Sales, Quantity, Avg. Discount)

## Insights Derived

- A **12.5%** increase in Total Sales compared to the previous period.
- Most sales occurred on **April 3, 2025**, with a peak of ~$700.
- The **North** and **East** regions generated the highest sales.
- **Credit Card** and **PayPal** are the preferred payment methods.
- **Product A** was the top-selling product with the highest revenue.

## How to Run

1. Install **Power BI Desktop** (if not installed).
2. Download or clone this repository.
3. Open `sales1.pbix` in Power BI Desktop.
4. Refresh the dataset if needed.
5. Explore the dashboard interactively!

## Acknowledgments

Thanks to the Power BI community and Microsoft documentation for supporting learning and development of interactive dashboards.

## Final Conclusion

The Power BI dashboard successfully provides a clear and interactive view of sales performance for the week of April 1–7, 2025.  
Key metrics such as total sales, orders, and items sold have shown positive growth.  
The analysis highlights top-performing products, dominant sales regions, and preferred payment methods, helping stakeholders quickly identify business opportunities and areas for improvement.  
Overall, the dashboard offers valuable insights to support better decision-making and sales strategies.

