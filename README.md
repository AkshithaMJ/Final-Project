# Snitch Fashion Sales Analytics
### End-to-End Data Analysis and Preprocessing Using Python

---

## Project Overview

This project focuses on analyzing and preprocessing a comprehensive sales dataset for **Snitch Fashion** using Python. The objective is to ensure data quality through systematic data cleaning, missing value imputation, outlier handling using the IQR method, feature engineering, and exploratory data analysis (EDA) supported by visual insights.

The cleaned dataset and visualizations provide a reliable foundation for understanding sales performance, product category trends, and profitability.

## Dataset Information

The dataset includes order details, product categories, sales amounts, units sold, unit prices, discounts, and customer information.

| Dataset Details | Information |
|---|---:|
| Target Domain | Fashion & E-commerce Sales |
| Key Operations | Data Cleaning, Imputation, Outlier Capping, Feature Engineering |
| Final Output | Cleaned CSV Dataset & Visualizations |

**Original Dataset:** `Snitch_Fashion_Sales_Uncleaned.csv`

## Tools and Technologies

- **Python** – Core programming language used for data analysis.
- **Jupyter Notebook** – Interactive environment used to execute and document the workflow.
- **Pandas & NumPy** – Used for data manipulation, imputation, and numerical calculations.
- **Matplotlib & Seaborn** – Used for generating exploratory data visualizations and plots.

## Data Pre-processing & Workflow

The analysis and preparation pipeline was structured into the following sequential steps:

### 1. Data Loading and Initial Inspection
- Imported the dataset using Pandas.
- Inspected dataset shape, column names, data types, and initial records using `head()`, `info()`, and `describe()`.

### 2. Missing Value Imputation & Cleaning
- Standardized column names and text formats.
- Handled missing values in `Units_Sold` and `Unit_Price` using median imputation.
- Replaced missing or zero values in `Units_Sold` with `1` to maintain realistic order quantities.
- Forward-filled (`ffill`) missing date entries in `Order_Date` to preserve chronological integrity.

### 3. Feature Engineering
Created derived categorical flags to assist in deeper business EDA and visualizations:
- `Profit_Status`: Categorized orders into `Profitable`, `Loss`, or `Break-even`.
- `Discount_Level`: Grouped discounts into `High Discount (>50%)` and `Normal Discount (<=50%)`.
- `Order_Size`: Classified orders into `Bulk Order`, `Single Order`, and `Return / Zero` using conditional logic.

### 4. Outlier Detection and Capping (IQR Method)
- Applied the Interquartile Range (IQR) method across numerical columns ('all numerical cells'.).
- Capped extreme anomalies using Winsorization (`.clip()`) to retain data distribution without losing valuable records.

### 5. Exploratory Data Analysis (Without Visualization)
- **GroupBy Analysis:** Aggregated `Sales_Amount`, `Profit`, and `Units_Sold` by `Product_Category` to evaluate category-level revenue and profit performance.
- **Pivot Table:** Built a cross-tabulated summary of `Sales_Amount` across `City` and `Segment` (`B2B`, `B2C`, `Unknown`).
- **Correlation Matrix:** Examined linear relationships among numerical variables (`Units_Sold`, `Unit_Price`, `Sales_Amount`, `Profit`).

### 6. Exploratory Data Analysis & Visualizations (10 Situation-Based Charts)
- Created **10 separate charts** tailored to each analytical situation using a **consistent purple theme** (`#4C1D95`, `#6D28D9`, `#A78BFA`) with titles, x-labels, y-labels, and pre-chart Markdown explanations:
  1. **Vertical Bar Chart:** Total Sales Amount by Product Category
  2. **Horizontal Bar Chart:** Total Profit by Product Category
  3. **Line Chart:** Monthly Sales Trend
  4. **Area Chart:** Monthly Profit Trend
  5. **Pie Chart:** Order Size Distribution (`Single Order`, `Bulk Order`, `Return / Zero`)
  6. **Donut Chart:** Discount Level Distribution (`High Discount (>50%)` vs `Normal Discount (<=50%)`)
  7. **Scatter Plot:** Unit Price vs. Sales Amount
  8. **Boxplot:** Sales Amount by Profit Status
  9. **Violin Plot:** Profit Distribution by Product Category
  10. **Heatmap:** Correlation Heatmap of Numerical Features

### 7. Exporting the Cleaned Dataset
Exported the final processed dataset into a separate CSV file for downstream reporting:

`Snitch Fashion Sales Cleaned.csv`

---

## Key Findings & Observations (10 Points)

1. **Top Revenue Category:** **Dresses** leads in total sales revenue, followed closely by **Jeans** and **T-Shirts**.
2. **Category Profitability:** **Dresses** also contributes strongly to total profit, while categories like **Shoes** and **Jackets** generate comparatively smaller profit totals.
3. **Monthly Sales Fluctuations:** Monthly `Sales_Amount` varies across the calendar year, reflecting seasonal demand shifts rather than uniform monthly sales.
4. **Monthly Profit Movement:** Monthly `Profit` fluctuates across months and does not always increase at the exact same pace as sales volume.
5. **Single Order Dominance:** **Single Orders** make up the largest share of transactions (`1,578` orders), followed by **Bulk Orders** (`639` orders).
6. **Return / Zero Impact:** Around `11.3%` (`283` out of `2,500`) of records fall under `Return / Zero`, showing that returns/adjustments affect net order volume.
7. **High Discount Share:** A large portion of transactions fall under `High Discount (>50%)` (median `0.65`), showing heavy reliance on promotional discounts.
8. **Sales Drivers:** `Units_Sold` shows a strong positive correlation with `Sales_Amount`, while `Unit_Price` shows a moderate positive relationship with sales revenue.
9. **Profit Status & Sales Spread:** Boxplot analysis across `Profit_Status` shows that loss-making transactions occur across varied sales amounts, meaning high sales alone does not guarantee profit.
10. **City & Segment Distribution:** Sales are distributed across cities such as **Mumbai, Ahmedabad, Hyderabad, Delhi, Bangalore, and Pune**, spanning **B2B**, **B2C**, and **Unknown** segments.

---

---

##  Project Summary

This project presents an end-to-end data cleaning, feature engineering, and exploratory data analysis (EDA) workflow on **2,500 retail transactions** across **12 core dimensions** for **Snitch Fashion**. After resolving missing values, standardizing city names and dates, engineering business features (`Profit_Status`, `Discount_Level`, `Order_Size`), and capping outliers using the IQR method, the dataset was analyzed both statistically (GroupBy, Pivot Table, Correlation Matrix) and visually using **10 situation-based charts** .

---

## Key Insights

- **Category Leaders:** **Dresses** generates the highest total sales revenue and net profit, followed closely by **Accessories**, **T-Shirts**, and **Jeans**, while **Shoes** trails in cumulative sales.
- **Volume vs. Price Impact:** Order quantity (`Units_Sold`) shows a strong positive correlation with `Sales_Amount` (`r = 0.86`), whereas `Unit_Price` shows a moderate positive relationship (`r = 0.22`).
- **Order Size & Returns:** **Single Orders** account for the largest share of transactions (`63.1%`), **Bulk Orders** make up `25.6%`, and **Return / Zero** entries account for `11.3%` (`283` out of `2,500` orders).
- **Heavy Discounting & Margin Trade-offs:** A large share of transactions fall under `High Discount (>50%)`, and boxplot/correlation findings show that higher sales amounts do not automatically guarantee higher profit when discounts or return adjustments occur.
- **Multi-City & Segment Reach:** Sales are distributed across major hubs (**Mumbai, Ahmedabad, Hyderabad, Delhi, Bangalore, Pune**) spanning **B2B**, **B2C**, and **Unknown** segments.

---

## Recommendations

- **Audit Deep Discounting (`>50%`):** Review promotional markdowns on lower-margin items and categories so steep discounts do not erode net profitability.
- **Reduce Return / Zero Transactions:** Investigate the `11.3%` (`283` records) return/zero volume—especially by category and order size—to improve sizing accuracy, product descriptions, and net revenue retention.
- **Prioritize Top Categories & Peak Months:** Align inventory stocking, bundle offers, and marketing campaigns with high-performing categories (**Dresses**, **Accessories**, **T-Shirts**, **Jeans**) and high-demand months.
- **Improve Segment & Data Capture:** Reduce `'Unknown'` entries in `Segment` and standardize data entry formats at the source to make future customer-level reporting more accurate.

---

##  Conclusion

The exploratory analysis of **Snitch Fashion** demonstrates that while order volume and top categories like **Dresses** drive strong revenue and multi-city reach, profitability is shaped by promotional discounting, return behavior, and order composition. Combining clean data preparation with structured statistical summaries and targeted visualizations provides a clear basis for pricing, inventory, and retention decisions.

---

##  Limitations and Considerations

- **Imputation & Capping Effects:** Missing values (`Unit_Price`, `Discount_%`, `Order_Date`, `Segment`) and extreme outliers capped via IQR improve analytical consistency, but imputed/capped values reflect statistical approximations rather than raw source records.
- **Zero Variance in Capped `Discount_%`:** After outlier capping/imputation concentrated `Discount_%` values around `0.65`, variance in that column became limited, which is why `Discount_%` was excluded from the numerical correlation matrix.
- **Missing Cost & Customer Metadata:** Detailed unit cost and unique customer IDs are not explicitly separated in the dataset, so profit and segment behavior are evaluated from the available transaction fields.
- **Multi-Year Aggregation:** Grouping by calendar month across multi-year entries blends seasonal patterns across years and should be interpreted alongside year-over-year context.

---

## Project Structure

```text
Snitch-Fashion-Sales-Analytics/
│
├── README.md
├── Snitch Fashion Sales Cleaned.ipynb
├── Snitch Fashion Sales Cleaned.csv
└── Snitch_Fashion_Sales_Uncleaned.csv

