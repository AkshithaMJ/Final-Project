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

### 5. Exploratory Data Analysis (EDA) & Visualizations
- Generated univariate, bivariate, and multivariate plots using Matplotlib and Seaborn.
- Created visualizations including count plots, bar charts, and distribution summaries to evaluate category sales and profit trends.

### 6. Exporting the Cleaned Dataset
Exported the final processed dataset into a separate CSV file for downstream reporting:

`Snitch Fashion Sales Cleaned.csv`

## Project Structure

```text
Snitch-Fashion-Sales-Analytics/
│
├── README.md
├── Snitch Fashion Sales Cleaned.ipynb
├── Snitch Fashion Sales Cleaned.csv
└── Snitch_Fashion_Sales_Uncleaned.csv
