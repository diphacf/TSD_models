# Electricity Load Forecasting: Statistical vs. ML vs. DL Approaches

## Project Overview
This project focuses on predicting electricity load consumption using three different approaches: **Statistical (VAR)**, **Machine Learning (XGBoost)**, and **Deep Learning (LSTM)**. The goal is to identify the most accurate model for short-term energy demand forecasting, which is crucial for grid stability and energy management.

## Dataset Information
- **Source:** Electricity Load Diagrams 2011-2014 (UCI Machine Learning Repository).
- **Format:** Hourly resampled time-series data.
- **Features:** Load (Target), Temperature, Humidity, Wind speed, and Hour of the day.

## Key Data Insights (EDA)
*Before modeling, I performed Exploratory Data Analysis to understand the data patterns:*
- **Seasonality:** High demand during specific hours of the day (Business hours).
- **Correlation:** Analyzed the relationship between weather variables (Temperature, Wind) and electricity load.

<img width="625" height="526" alt="Correlation Matrix" src="https://github.com/user-attachments/assets/7d3fe2d2-f6ab-49f1-af49-c7b55bc6a66e" />


## Methodology
1. **Data Preprocessing:** Handled missing values (zeros), resampled to hourly frequency, and performed feature scaling using `StandardScaler`.
2. **Feature Engineering:** Created lag features (1-24h), rolling means, and rolling standard deviations to capture temporal trends.
3. **Modeling:**
   - **VAR (Vector Autoregression):** A traditional statistical model for multivariate time series.
   - **XGBoost:** A powerful gradient boosting algorithm with custom time-series features.
   - **LSTM (Long Short-Term Memory):** A Recurrent Neural Network (RNN) designed to learn long-term dependencies.

## Results & Comparison
| Model   | RMSE  | MAE   | MAPE (%) | Accuracy (%) |
|---------|-------|-------|----------|--------------|
| **VAR**     | 19.94 | 18.28 | 71.29%   | 28.71%       |
| **XGBoost** | 0.47  | 0.14  | 0.74%    | 99.26%       |
| **LSTM**    | 3.63  | 2.87  | 12.01%   | 87.99%       |

### **Backtesting Visualization**
The following chart compares the predictions of all three models against the actual load for the last 100 hours of the test set:

<img width="1209" height="449" alt="Comparison of All Models" src="https://github.com/user-attachments/assets/2ac2d25c-eb6a-4c66-a2bf-7eb524af71b5" />


## Business Insights for Data Analyst Position
- **Model Selection:** XGBoost significantly outperformed other models in this specific dataset, making it the most reliable for short-term forecasting.
- **Actionable Advice:** Energy providers can use the XGBoost model to predict peak loads with >99% accuracy, allowing for better resource allocation and cost reduction.

## How to Run
1. Clone the repository:
   ```bash

   git clone https://github.com/diphacf/TSD_models.git

2. Install dependencies:
   ```bash

   pip install -r requirements.txt

3. Open TSD_models.ipynb and run all cells.
