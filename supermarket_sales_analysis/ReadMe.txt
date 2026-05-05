# 🛒 Supermarket Sales Analysis

A dual-tool data analysis project combining **Python (Jupyter Notebook)** for data processing and **Power BI** for interactive visualization — analyzing supermarket sales performance across product categories, profitability, and time-based trends.

---

## 📊 Dashboard Preview

![Supermarket Sales Dashboard](dashboard.png)

---

## 🔢 Key Metrics

| Metric | Value |
|---|---|
| Total Revenue | 128.89K |
| Total Profit | 146.45K |
| Total Quantity Sold | 14.29K |
| Overall Profit Margin | 113.6% |

---

## 📈 Key Insights

- **Capsicum** is the most profitable category with a profit margin of **178.1%**
- **Broccoli** is the top-selling product with **12.1K** in revenue
- **Flower/Leaf Vegetables** leads all categories in revenue at **52K**
- **July** significantly outperformed **August** in monthly revenue (123K vs 6K)
- All top categories maintain profit margins above **70%**
- Effective margin was calculated accounting for product **loss rates** per item

---

## 🗂️ Project Structure

```
supermarket-sales-analysis/
│
├── supermarket_sales_analysis.ipynb   # Python analysis notebook
├── annex1.csv                         # Items (item codes + categories)
├── annex2.csv                         # Sales transactions
├── annex3.csv                         # Wholesale prices
├── annex4.csv                         # Loss rates
├── sales.csv                          # Merged dataset (output)
├── sales_cleaned.csv                  # Final cleaned dataset (output)
├── dashboard.png                      # Power BI dashboard screenshot
└── README.md
```

---

## 🐍 Python Analysis (Jupyter Notebook)

### Data Sources
Four CSV files were loaded and merged into a single fact table:

| File | Contents |
|---|---|
| `annex1.csv` | Item codes and category names |
| `annex2.csv` | Sales transactions (quantity, price, date) |
| `annex3.csv` | Wholesale prices per item per date |
| `annex4.csv` | Loss rates per item |

### Data Cleaning Steps
- Converted date columns to proper `datetime` format
- Standardized all column headers (lowercase, underscores, stripped whitespace)
- Checked all four files for null values
- Merged all files into one master `sales` DataFrame using left joins

### Feature Engineering
```python
# Revenue
sales['revenue'] = sales['quantity_sold_(kilo)'] * sales['unit_selling_price_(rmb/kg)']

# Margin
sales['margin'] = sales['unit_selling_price_(rmb/kg)'] - sales['wholesale_price_(rmb/kg)']

# Effective Margin (accounting for loss rate)
sales['effective_margin'] = sales['margin'] * (1 - sales['loss_rate_(%)'] / 100)

# Profit per item
sales['profit_per_item'] = sales['unit_selling_price_(rmb/kg)'] - sales['wholesale_price_(rmb/kg)']

# Overall profit margin
profit_margin = round(total_profit / total_revenue * 100, 2)
```

### Analysis Performed

**Sales Performance**
- Total revenue, total quantity sold, average sales
- Daily revenue trends

**Product-Level Insights**
- Most sold product categories
- Category revenue rankings
- Top 5 selling items by quantity
- Items performing below average revenue

**Profitability**
- Profit per item
- Most profitable categories
- Overall profit margin calculation

**Time-Based Analysis**
- Day with highest sales
- Month with highest sales
- Monthly revenue trends and seasonal patterns

---

## 📊 Power BI Dashboard

### Visuals Included
- **KPI Cards** — Total Revenue, Total Profit, Quantity Sold, Profit Margin
- **Monthly Revenue** — Bar chart comparing July vs August
- **Profit Margin per Category** — Horizontal bar chart ranked by margin
- **Top 5 Products** — Best performing products by revenue
- **Revenue per Category** — Category-level revenue comparison
- **Interactive Slicer** — Filter by Category Code

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Python (pandas, numpy) | Data loading, cleaning, merging, feature engineering |
| Matplotlib / Seaborn | Data visualization |
| Jupyter Notebook | Exploratory data analysis |
| Power BI Desktop | Interactive dashboard |
| DAX | Calculated measures and KPIs |
| Power Query | Data transformation in Power BI |

---

## 🚀 How to Run

**Python Notebook:**
1. Clone this repository
2. Install dependencies: `pip install pandas numpy matplotlib seaborn`
3. Open `supermarket_sales_analysis.ipynb` in Jupyter
4. Run all cells in order

**Power BI Dashboard:**
1. Open the `.pbix` file in Power BI Desktop
2. Use the Category Code slicer to filter by specific categories
3. Hover over visuals for detailed tooltips

---

## 👤 Author

**Olawande**
Data Analyst | Python | Power BI | SQL

> *"Turning raw data into business decisions."*