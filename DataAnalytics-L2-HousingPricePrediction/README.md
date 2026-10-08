# Data Analytics - Level 2 - House Price Prediction

*Internship:* Oasis Infobyte SIP, Data Analytics track, Level 2, Task 1
*Author:* Oluchi (GitHub: Oluchi-Lucy)

# Project overview
A Linear Regression model that predicts house prices from district features such as income, house age, rooms and location, using Python and scikit-learn.

# Dataset
The California Housing dataset, loaded directly from scikit-learn (fetch_california_housing). It has 20,640 districts, 8 features and no missing values. A copy is saved as california_housing.csv. The price column (MedHouseVal) is in units of 100,000 dollars and is capped at 5.0. The dataset has no category columns, so one-hot encoding was not needed.

# Tools
Python 3, pandas, NumPy, scikit-learn, Matplotlib, Seaborn, Jupyter Notebook

# Files in this folder
- DataAnalytics-L2-HousePricePrediction.ipynb: the full notebook
- california_housing.csv: the dataset

# Method
1. Explored the data: descriptive statistics and the distribution of the target price.
2. Correlation heatmap and a feature selection discussion. All 8 features were kept.
3. Split the data 80/20 (16,512 training rows, 4,128 test rows).
4. Trained a Linear Regression model.
5. Evaluated it with MSE, RMSE and R-squared.
6. Plotted actual vs predicted prices and a residual plot.
7. Analysed the coefficients.

# Results

| Metric | Result |
|---|---|
| MSE | 0.5559 |
| RMSE | 0.7456 |
| R-squared | 0.5758 |

The model explains about 57.6% of the variation in house prices. The RMSE of 0.7456 means predictions are off by about 75,000 dollars on average.

# Key findings
- Median income (MedInc) has the strongest link to price (correlation 0.69).
- The model follows the general trend but predicts too low for expensive districts, and it cannot handle the price cap at 5.0.
- The biggest positive coefficient is AveBedrms (0.78), then MedInc (0.45). The biggest negative ones are Longitude (-0.43) and Latitude (-0.42).
- AveRooms and AveBedrms are strongly linked (0.85), and Latitude and Longitude are strongly linked (-0.92), so their individual coefficients should be read with care.

# Possible improvements
Try Ridge or Lasso regression, or non-linear models such as Random Forest, and handle the 5.0 price cap.

# How to run
1. Download this folder.
2. Open DataAnalytics-L2-HousePricePrediction.ipynb in Jupyter Notebook.
3. Run all cells (the notebook loads the data from scikit-learn, so it needs an internet connection).
