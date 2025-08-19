# Walmart-Demand-Forecasting-M5-
Project Overview:- The goal of this project is to forecast daily product demand for Walmart stores using historical sales data, price information, and calendar events. Accurate demand forecasting helps Walmart optimize inventory management, reduce costs from overstocking or stockouts, and improve customer satisfaction.

ML Task: Multi-step time-series regression to predict sales for the next 28 days for each product-store combination.
Dataset:- Source: Kaggle M5 Forecasting (Accuracy) Competition
File used:- 
  1.sales_train_validation.csv → Historical daily sales of 30k+ products.
  2.calendar.csv → Holidays, events, and special days.
  3.sell_prices.csv → Product price history.

Walmart Demand Forecasting – Project Phases

Phase 1 – Problem Statement:
The goal of this project is to predict daily product demand for Walmart stores to help optimize inventory and reduce costs due to overstocking or stockouts. Predicting future sales enables better planning for promotions, seasonal demand, and overall supply chain efficiency. The machine learning task is framed as a multi-step time-series regression, where the target variable is daily sales for each product-store, and features include historical sales, price trends, and calendar events.

Phase 2:- We collected the M5 Forecasting dataset from Kaggle, which includes:sales_train_validation.csv → Historical daily sales for 30k+ products,calendar.csv → Holiday, events, and special day indicators, sell_prices.csv → Product price history
The dataset has a daily granularity, and the forecast horizon is 28 days.

Phase 3 – Exploratory Data Analysis (EDA):
EDA was performed to understand sales trends, seasonality, and data quality issues. Key observations included: Holidays and special events cause spikes in sales, Price reductions often lead to higher sales in certain categories, Some products have consistently low demand, while others are seasonal, We also checked for missing values, duplicates, and inconsistencies.

Phase 4 – Data Preprocessing & Feature Engineering:
Data preprocessing involved handling missing values, encoding categorical variables (store, product, event types), and merging all datasets. Feature engineering included: Lag features (sales from previous 7, 14, 28 days), Rolling averages (7-day, 14-day sales), Price features (current and past prices, price change trends), Event indicators (holidays, weekends, special events)

Phase 5 – Model Training:
We trained multiple models to forecast sales: LightGBM → Main model due to efficiency on large tabular datasets, XGBoost → Alternative boosting model for comparison, Random Forest Regressor → Baseline model, Hyperparameter tuning was done for LightGBM using cross-validation with a rolling window approach to respect time-series data.

Phase 6 – Model Evaluation & Forecast Output: The final model was evaluated using: RMSE (Root Mean Square Error), WMAPE (Weighted Mean Absolute Percentage Error), MAPE (Mean Absolute Percentage Error), The model generated 28-day sales forecasts for each product-store combination. Visualizations were created to compare predicted vs actual sales and to display feature importance.

