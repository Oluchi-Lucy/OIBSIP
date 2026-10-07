# Data Analytics - Level 1 - EDA on Retail Sales

*Internship:* Oasis Infobyte SIP, Data Analytics track, Level 1, Task 1
*Author:* Oluchi (GitHub: Oluchi-Lucy)

# Project overview
Exploratory data analysis of a retail sales dataset (1,000 transactions, 9 columns) to find sales trends, customer patterns and business recommendations, using Python.

# Dataset
"Retail Sales Dataset" from Kaggle (Mohammad Talib). The file used is included as retail_sales_dataset.xlsx. It has no missing values and no duplicates. Dates are stored as Excel numbers, so they were converted to real dates.

# Tools
Python 3, pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook

# Files in this folder
- DataAnalytics-L1-EDARetailSales.ipynb: the full analysis notebook
- retail_sales_dataset.xlsx: the dataset

# What the analysis covers
1. Data inspection: shape, data types, missing values, duplicates
2. Descriptive statistics: mean, median, mode, standard deviation
3. Time series: monthly and quarterly sales (2023 only; 2 transactions dated 2024-01-01 were excluded from the trend)
4. Customer demographics: age groups and gender
5. Product analysis: revenue by category (the dataset has 3 categories and no product names, so categories are ranked instead of a top 10 products list)
6. Correlation heatmap
7. Extra chart: share of transactions vs share of revenue by price point
8. Conclusion with 3 business recommendations

# Key findings
- Total revenue is 456,000 across 1,000 transactions. The average transaction is 456, but the median is 135.
- Sales peaked in May (53,150) and were lowest in September (23,620). Q4 was the strongest quarter (126,190).
- Electronics (34.4%) and Clothing (34.1%) are almost tied for revenue. Beauty is lowest (31.5%).
- Customers are spread fairly evenly across age groups, and gender is nearly even (51% female, 49% male).
- Price per Unit has the strongest link to Total Amount (0.85). Age has almost none (-0.06).
- *The two highest price points (300 and 500) make up 39.6% of transactions but 88.4% of revenue.*

# Recommendations
1. Prioritise high-priced products in stock, shelf space and promotions.
2. Plan around the sales swings: promote in September and Q3, stock up before May and Q4.
3. Target the weakest segments: customers aged 18-24 and the Beauty category.


