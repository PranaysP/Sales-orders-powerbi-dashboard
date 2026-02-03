# Sales-orders-powerbi-dashboard
End-to-end Power BI Sales &amp; Orders dashboard with DAX, KPIs, and business insights.
📊 Sales & Orders Power BI Dashboard
🔍 Project Overview

This project demonstrates an end-to-end Business Intelligence solution built using Power BI to analyze sales, profit, and operational performance from transactional order data.

The dashboard provides insights into sales trends, product performance, regional contribution, profitability, and order efficiency.

🛠 Tools & Technologies

Power BI Desktop

DAX (Data Analysis Expressions)

Excel (Source Data)

📌 Key KPIs

Total Sales

Total Cost

Total Profit

Profit Margin %

Total Quantity Sold

Year-over-Year (YoY) Sales Growth %

<img width="1187" height="106" alt="image" src="https://github.com/user-attachments/assets/d3e041e5-0e6a-4300-9e96-ec6fd427e8e7" />

📈 Dashboard Features

Sales trend analysis by Year & Month

Product-wise Sales and Profit analysis

Region-wise Sales distribution

<img width="1096" height="283" alt="image" src="https://github.com/user-attachments/assets/ea0d779e-aff1-428c-80c2-ca62f8c61027" />

Product-wise Profit contribution

Country-wise Profit contribution

Quantity vs Profit correlation analysis

<img width="1111" height="278" alt="image" src="https://github.com/user-attachments/assets/87862174-8f1a-4696-bca9-a16697c62e9b" />

Interactive filters (Country, Region, Product)

<img width="105" height="569" alt="image" src="https://github.com/user-attachments/assets/a3bd1dd8-6c52-4cf2-b89c-26eb0a8f2a39" />


📐 DAX Measures Used

Total Sales = SUMX(Orders, Orders[Quantity] * Orders[Price])
Total Profit = [Total Sales] - [Total Cost]
Profit Margin % = DIVIDE([Total Profit], [Total Sales])
YoY_Sales_Growth % = DIVIDE([Total_sales] - [Lastyear_sales], [Lastyear_sales])
Lastyear_sales = CALCULATE([Total_sales],SAMEPERIODLASTYEAR(Sales[Order Date].[Date]))
Previous_month_sales = CALCULATE([Total_sales],PREVIOUSMONTH(Sales[Order Date].[Month]))
Running_Total = CALCULATE([Total_sales],FILTER(ALLSELECTED(Sales[Order Date]),Sales[Order Date] <= MAX(Sales[Order Date])))
Top N sales = RANKX(ALL(Sales[Products]),[Total_sales],,DESC)
Delivery_Days = DATEDIFF(Sales[Order Date],Sales[Shipped Date],DAY)
2ndMax_date = MAXX(FILTER(Sales,Sales[Order Date] < MAX(Sales[Order Date])), Sales[Order Date].[Date])

🖼 Dashboard Preview

<img width="1278" height="687" alt="image" src="https://github.com/user-attachments/assets/2208a4fa-e0e1-4460-b178-f8c225007230" />

💡 Business Insights

Butter and Cake contribute the highest revenue and profit

West region drives over 50% of total sales

China is the top profit-generating country

Strong positive correlation between quantity and profit

🚀 Future Enhancements

Drill-through analysis (Region → Product)

Forecasting and trend prediction

Row-level security (RLS)

Power BI Service deployment
