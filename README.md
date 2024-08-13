# Sales Performance Dashboard

Welcome to the Sales Performance Dashboard project! This Power BI dashboard is designed to provide actionable insights into sales performance, helping businesses make data-driven decisions and improve their strategic planning.

## Project Overview
The Sales Performance Dashboard integrates data from various sources to deliver a comprehensive analysis of sales metrics. It features three key sheets, each addressing different aspects of sales performance:
#### 1. Sales Overview: Key Metrics & Trends
- Purpose: Offers a high-level snapshot of sales performance.  
- Benefits: Quickly assess overall sales health, identify key trends, and evaluate market performance.
#### 2. Detailed Profit Breakdown & Market Analysis
- Purpose: Analyzes profitability and market contributions.  
- Benefits: Helps in understanding revenue and profit dynamics by market and customer, guiding targeted strategies for improvement.
#### 3. Market Performance Comparison & Yearly Trends
- Purpose: Compares market performance across years and highlights areas needing attention.  
- Benefits: Identifies performance gaps, tracks trends, and helps in making strategic adjustments to meet profit targets.

## Steps Followed:
- Step 1: Load the data into Power BI. Dataset is SQL file.  

- Step 2: Use Power Query Editor for Data cleaning and Data Normalization such as some sales amount shows 0 or -1 values, some null values were there in currency, fix the date format, use conditional formatting to sort the months etc.

- Step 3: Create some new measures using DAX. Those are followings:

        i.	Revenue = SUM('sales transactions'[sales_amount])  
        ii.	Total Cost = SUM('sales transactions'[cost price])  
        iii.	Sales Quantity = SUM('sales transactions'[sales_qty])
        iv.	date normalize = DATE('sales date'[year],'sales date'[Month],01)  
        v.	Profit = [Revenue] - [Total Cost]  
        vi.	Profit Margin % = DIVIDE([Total Profit Margin],[Revenue],0)  
        vii.	Total Profit Margin = SUM('sales transactions'[profit_margin])  
        viii.	Profit Margin Contribution % = DIVIDE([Total Profit Margin], CALCULATE([Total Profit Margin],ALL('sales customers'), ALL('sales products'), ALL('sales markets')))   
        ix.	Profit Margin Difference = [Profit Margin %] - 'Profit Target'[Profit Target Value 2]  
        x.	Revenue Contribution % = DIVIDE([Revenue], CALCULATE([Revenue],ALL('sales customers'), ALL('sales products'), ALL('sales markets')))  

- Step 4: Create Visualization:
    - Cards: Revenue, Sales Quantity, Total Cost, Profit, Total Profit Margin
    -	Line Chart: Revenue by Date
    -	Line and Column Chart: Last and Current Year Revenue with Profit Margin
    -	Bar Chart: Revenue by market, Sales Quantity by market, Top Customers, Top Products, Profit Percentage by Market, Profit Contribution by Market, Revenue Contribution by Market.
    -	Matrix: Customer Contribution
    -	Slicer: Year & Month (Tile), Profit Target (Single Value)


## Key Insights from the Sales Performance Dashboard:
#### i.	Overall Financial Performance:
- Total Revenue: ₹985M
- Total Sales: 2M units
- Total Profit: ₹24.6M
- Summary: The business demonstrates strong profitability with substantial revenue and profit margins.
#### ii.	Regional Sales Analysis:
- North Zone: Leading in sales volume with a total revenue of ₹676M, primarily from physical sales.
- Central Zone: Shows the highest profit margin of ₹8.6M, while the North Zone contributes the most to overall profit at 60%.
#### iii.	Top-performing Cities:
- Delhi NCR: Achieved the highest revenue at ₹520M, highest sales volume with 988K units, and the greatest profit contribution at 48%.
- Surat: Exhibits the highest profit margin at 4.9%.
#### iv.	Revenue Trend Analysis:
- Significant Growth: Revenue surged in 2018-2019, with peaks of ₹32M in January 2018 and ₹31M in August 2018.
- Decline in 2020: Revenue declined sharply to ₹11M in June 2020, possibly due to the impact of COVID-19.


