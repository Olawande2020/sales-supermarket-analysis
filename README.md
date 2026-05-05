# Supermarket Sales Analysis
A dual-tool data analysis project combining Python (Jupyter Notebook) for data processing and Power BI for interactive visualization analyzing supermarket sales performance across product categories, profitability, and time-based trends.

## Dashboard Preview
<img width="623" height="338" alt="image" src="https://github.com/user-attachments/assets/b97c69e5-f390-4313-8fd7-47d0e2e6b98d" />


## Key Metrics
- MetricValueTotal Revenue128.89K
- Total Profit146.45K
- Total Quantity Sold14.29K
- Overall Profit Margin113.6%

## Key Insights
- Capsicum is the most profitable category with a profit margin of 178.1%
- Broccoli is the top-selling product with 12.1K in revenue
- Flower/Leaf Vegetables leads all categories in revenue at 52K
- July significantly outperformed August in monthly revenue (123K vs 6K)
- All top categories maintain profit margins above 70%
- Effective margin was calculated accounting for product loss rates per item

## Python Analysis (Jupyter Notebook)
- Data Sources
- Four CSV files were loaded and merged into a single fact table:
-- FileContentsannex1.csvItem codes and category namesannex2.csvSales transactions (quantity, price, date)annex3.csvWholesale prices per item per dateannex4.csvLoss rates per item
  
## Data Cleaning Steps
- Converted date columns to proper datetime format
- Standardized all column headers (lowercase, underscores, stripped whitespace)
- Checked all four files for null values
- Merged all files into one master sales DataFrame using left joins

## Product-Level Insights
- Most sold product categories
- Category revenue rankings
- Top 5 selling items by quantity
- Items performing below average revenue

## Profitability
- Profit per item
- Most profitable categories
- Overall profit margin calculation

## Time-Based Analysis
- Day with highest sales
- Month with highest sales
- Monthly revenue trends and seasonal patterns

## Tools & Technologies
- ToolPurposePython (pandas, numpy)Data loading, cleaning, merging, feature engineeringMatplotlib / SeabornData visualization
- Jupyter Notebook
- Exploratory data analysis
- Power BI DesktopInteractive dashboard
- DAXCalculated measures and KPIs
- Power QueryData transformation in Power BI
