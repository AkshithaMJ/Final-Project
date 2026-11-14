# 🛍️ Snitch Fashion Sales — Data Cleaning 
## 📌 Project Overview
This project focuses on end-to-end Data Cleaning, Pre-processing, and Feature Engineering on the Snitch Fashion Sales Dataset using Python (Pandas & NumPy). 
The goal is to transform raw, inconsistent retail sales data into a clean, structured, and analysis-ready dataset suitable for Exploratory Data Analysis (EDA) and business intelligence reporting.
### 📂 Dataset SummaryRaw Dataset: 
Snitch_Fashion_Sales_Uncleaned.csv (2,501 rows, 12 columns)
### Cleaned Dataset: 
Snitch_Fashion_Sales_Final_Cleaned.csv (2,501 rows, 19 columns)
### Domain: 
E-Commerce & Fashion Retail
## 🛠️ Key Data Cleaning & Pre-processing Steps 
Duplicate Removal:Verified and removed any duplicate records to ensure data integrity.
Standardizing Categorical Text (City):Fixed inconsistent spelling and casing variations (e.g., mapped bengaluru - Bangalore, and Hyd / hyderbad - Hyderabad).
Handling Returns & Missing Quantities (Units_Sold):Imputed missing Units_Sold values with 0.
Identified negative Units_Sold values as product returns rather than data errors, flagging them under a new Units_Sold_Status column (Returned vs. Delivered).
Category-Based Price Imputation (Unit_Price):Imputed missing Unit_Price values using the median price per Product_Category to prevent skewness from high-ticket items.
Correcting Discount Anomalies (Discount_%):Fixed invalid discount entries exceeding 100% (up to 130%) and filled missing discount entries using the dataset median (0.65).
Standardizing Mixed Date Formats (Order_Date):Parsed inconsistent date formats (YYYY-MM-DD, DD-MM-YYYY, YYYY/MM/DD) into a unified YYYY-MM-DD standard.
Labeled missing dates as "Unknown" to avoid data loss while extracting Order_Month and Order_Year for time-series analysis.
Handling Missing Customer Segments (Segment):Replaced missing values in Segment with "Unknown" to preserve row-level sales data without introducing bias.
## ⚙️ Feature Engineering 
(Derived Columns)To enable deeper business insights, 7 new analytical columns were engineered:Units_Sold_Status: Classifies orders as Delivered or Returned.
Order_Month & Order_Year: Extracted from standardized order dates for seasonality and trend analysis.
Profit_Status: Categorizes transactions into Profitable, Loss, or Break-even.
Discount_Level: Segments orders into High Discount (>50%) and Normal Discount (<=50%).
Order_Size: Distinguishes between Single / Return / Zero orders and Bulk Order (1+ Units).
## 💻 Tech StackLanguage:
Python 3Libraries: Pandas, NumPyEnvironment: Google Colab / Jupyter Notebook
