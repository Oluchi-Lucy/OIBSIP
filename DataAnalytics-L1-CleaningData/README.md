# Data Analytics - Level 1 - Cleaning Data

Internship: Oasis Infobyte SIP, Data Analytics track, Level 1, Task 3
Author: Oluchi (GitHub: Oluchi-Lucy)

# Project overview
I took a deliberately messy cafe sales dataset (10,000 rows, 8 columns) and turned it into a clean, analysis-ready dataset using Python. Every cleaning decision is documented in the notebook.

# Dataset
"Cafe Sales - Dirty Data for Cleaning Training" by Ahmed Mohamed on Kaggle (licence: CC BY-SA 4.0). The original file is included as dirty_cafe_sales.xlsx.

# Tools
Python 3, pandas, NumPy, Jupyter Notebook

# Files in this folder
- DataAnalytics-L1-CleaningData.ipynb: the full cleaning notebook
- dirty_cafe_sales.xlsx: the original messy dataset
- cleaned_cafe_sales.csv: the cleaned dataset (9,974 rows)

# What I found
- 6,826 blank cells, plus 3,256 hidden "ERROR" and "UNKNOWN" placeholders, which is 10,082 problem cells in total
- Quantity, Price Per Unit and Total Spent stored as text
- Transaction Date stored as Excel serial numbers (for example 45177)
- No duplicate rows

# Cleaning steps and decisions
1. Converted ERROR / UNKNOWN placeholders to proper missing values.
2. Converted the number columns to numeric and Transaction Date to real dates (2023-01-01 to 2023-12-31).
3. Total Spent = Quantity x Price Per Unit held in all 8,544 complete rows, so I used it to recalculate missing values (462 Total Spent, 441 Quantity, 495 Price Per Unit).
4. Each item has exactly one price, so I filled 32 missing prices from Item. A second calculation pass then recovered 17 Total Spent and 15 Quantity values.
5. Filled 489 missing Item values where the price belongs to one item only (1 = Cookie, 1.5 = Tea, 2 = Coffee, 5 = Salad). Prices 3 and 4 are shared by two items each, so I did not guess.
6. Dropped 26 rows (0.26%) where a numeric value could not be recovered.
7. Labelled the remaining missing Item, Payment Method and Location values as "Unknown" instead of dropping about 40% of the data.
8. Left 460 missing Transaction Dates blank, because a date cannot be guessed.
9. Ran IQR outlier detection. Quantity and Price Per Unit had none. Total Spent had 268 flagged values, all of them 5 Salads at 5 each = 25, a valid order, so I kept them.
10. Converted Quantity to whole numbers and saved the cleaned data to CSV.

# Before vs after

| Metric | Before | After |
|---|---|---|
| Row count | 10000 | 9974 |
| Blank (null) cells | 6826 | 460 |
| ERROR/UNKNOWN placeholder cells | 3256 | 0 |
| Total missing/invalid cells | 10082 | 460 |
| Duplicate rows | 0 | 0 |
| Cells labelled 'Unknown' (deliberate) | 0 | 7594 |
| Columns with correct data type | 4 of 8 | 8 of 8 |

# How to run
1. Download this folder.
2. Open DataAnalytics-L1-CleaningData.ipynb in Jupyter Notebook.
3. Keep dirty_cafe_sales.xlsx in the same folder and run all cells
