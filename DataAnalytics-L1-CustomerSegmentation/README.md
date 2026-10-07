# Data Analytics - Level 1 - Customer Segmentation

*Internship:* Oasis Infobyte SIP, Data Analytics track, Level 1, Task 2
*Author:* Oluchi (GitHub: Oluchi-Lucy)

# Project overview
Customer segmentation using K-Means clustering on a retail sales dataset (1,000 customers), to group customers by behaviour and suggest a marketing action for each group.

# Dataset
"Retail Sales Dataset" from Kaggle (Mohammad Talib), included as retail_sales_dataset.xlsx. It has no missing values and no duplicates. Each customer made only one purchase.

# Tools
Python 3, pandas, NumPy, scikit-learn (KMeans, StandardScaler), Matplotlib, Seaborn, Jupyter Notebook

# Files in this folder
- DataAnalytics-L1-CustomerSegmentation.ipynb: the full notebook
- retail_sales_dataset.xlsx: the dataset

# Method
1. Loaded and checked the data. Average purchase value is 456, with 1 purchase per customer.
2. Because each customer bought only once, Recency, Frequency and customer lifetime value could not be calculated. Clustering used Age, Quantity and Total Amount instead.
3. Scaled the features with StandardScaler.
4. Used the Elbow Method (K = 1 to 8). The bend is gentle, so K = 4 was chosen because it gives clear, usable groups.
5. Ran K-Means (K = 4) and profiled each cluster.
6. Visualised the clusters with scatter plots (Age vs Total Amount, Quantity vs Total Amount) and a bar chart of customers per cluster.

# Segments

| Cluster | Segment | Customers | Avg Age | Avg Quantity | Avg Total Amount | Share of revenue |
|---|---|---|---|---|---|---|
| 2 | High-value shoppers | 228 | 39.6 | 3.4 | 1,344.7 | 67.2% |
| 0 | Mature light spenders | 283 | 52.3 | 1.5 | 233.1 | 14.5% |
| 1 | Young light spenders | 240 | 26.8 | 1.7 | 211.4 | 11.1% |
| 3 | Bulk buyers of low-priced items | 249 | 44.6 | 3.6 | 131.3 | 7.2% |

# Marketing recommendations
1. *High-value shoppers:* 22.8% of customers bring 67.2% of revenue. Protect them with a VIP or loyalty programme and premium bundles.
2. *Mature light spenders:* email and in-store offers, loyalty points, higher-value product suggestions.
3. *Young light spenders:* social media campaigns, first-purchase discounts and trade-up offers.
4. *Bulk buyers of low-priced items:* cross-sell and upsell higher-priced items, with bundle and minimum-spend offers.

# How to run
1. Download this folder.
2. Open DataAnalytics-L1-CustomerSegmentation.ipynb in Jupyter Notebook.
3. Keep retail_sales_dataset.xlsx in the same folder and run all cells
