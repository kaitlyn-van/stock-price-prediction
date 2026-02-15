# 📈 Stock Price Prediction (NASDAQ: DXCM)

This project builds a machine learning model to predict the next trading day's closing price using historical market data from the Alpaca API.

## 🔍 Project Overview

- **Data Source:** Alpaca Market Data API
- **Asset:** DXCM (Dexcom, Inc.)
- **Frequency:** Daily bars
- **Start Date:** 2010-01-01
- **Target:** Next-day closing price
- **Model:** RandomForestRegressor

The goal is to explore whether technical indicators alone can provide predictive signal for short-term equity price movements.

## 🧠 Features Used

The model uses purely technical features derived from historical OHLCV data:

- Daily return
- 5-day rolling volatility
- **Moving averages (MA):**
    - MA(5)
    - MA(10)
    - MA(20)
    - MA(50)
    - MA(100)
- Current closing price

These features attempt to capture short-term momentum, volatility regimes, and trend structure.

## 📊 Evaluation Methodology

The dataset is split chronologically:
- First 80% → Training
- Last 20% → Testing

No random shuffling is used to prevent data leakage.

Performance is evaluated using **Mean Absolute Error (MAE)**.

Additionally, the model is compared against a naive baseline:
- **Baseline:** Tomorrow’s price = Today’s price

## 🚀 How to Run

1. Install dependencies:

```
pip install alpaca-py scikit-learn numpy matplotlib
```

2. Set environment variables:

```
export API_KEY=your_key
export API_SECRET=your_secret
```

3. Run the notebook.

## 📎 Disclaimer

This project is for educational purposes only.
It does not constitute financial advice or a trading strategy.