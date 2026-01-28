# dual-core-financial-intelligence
Stock price forecasting with uncertainty and explainable financial insights

# Dual-Core Financial Intelligence System

This project implements a dual-core financial intelligence system consisting of:
1. A **Predictive Core** for time-series stock price forecasting with uncertainty.
2. An **Explanatory Core** that translates model outputs into human-readable financial insights.

## Task 1: Predictive Core
- Asset: Apple Inc. (AAPL)
- Data: Daily historical stock prices (OHLCV)
- Model: SARIMA (Statistical Time Series Model)
- Forecast Horizon: 7 days
- Outputs:
  - Historical trend visualization
  - Validation on past unseen data
  - 7-day forecast
  - Confidence intervals to model uncertainty

## Task 2: Explanatory Core
A rule-based financial advisor layer interprets:
- Recent price trends
- Market volatility
- Forecast uncertainty

This allows the system to explain *why* a certain forecast is made, rather than providing only numerical predictions.

## Notes on Evaluation
The model is evaluated using Mean Absolute Error (MAE) on historical data.  
Absolute error values are relatively high due to long-term price growth and scale effects in stock prices.  
Future improvements include log-scaling and relative error metrics.

## Data Source
Historical stock price data sourced from **Stooq** (public financial data provider).

## Technologies Used
- Python
- Pandas, NumPy
- Statsmodels (SARIMA)
- Matplotlib
