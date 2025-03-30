# Bitcoin Price Forecasting: ARIMA vs. LSTM vs. Prophet

![screenshot-localhost_8888-2025 03 30-11_17_25](https://github.com/user-attachments/assets/29f141c3-8d5c-4ebb-bb16-57c993e1ab83)

## Overview

A comparative analysis of statistical and machine learning models for cryptocurrency price prediction, with actionable insights for traders and researchers.

### Project Overview

This project implements and compares three forecasting models for Bitcoin (BTC) prices:

- ARIMA (Traditional time-series modeling)
- LSTM (Deep learning for sequential data)
- Facebook Prophet (Additive regression with interpretability)

### Dataset

The dataset contains Bitcoin price data at 1-minute intervals (high-frequency data). The columns include:

- **Timestamp:** Unix timestamp (epoch time).
- **Open:** The price at the start of the minute.
- **High:** The highest price reached during the minute.
- **Low:** The lowest price reached during the minute.
- **Close:** The final price at the end of the minute.
- **Volume:** The number of Bitcoins traded during that minute.
- **datetime:** A converted, human-readable timestamp.

The dataset starts at January 1, 2012 and contains data points up to at least January 3, 2012.

### Key Steps in the Workflow

1. Data cleaning

2. Model training
- Differencing (ARIMA), sequence modeling (LSTM), and uncertainty intervals (Prophet)

3. Evaluation

4. Visualization
  
### Model Performance

- ARIMA	9,170.62
- LSTM	8,927.45
- Prophet	9,264.85

### Key Findings

1. LSTM achieved the lowest RMSE (8,927) but showed signs of overfitting (validation loss ↑). 

  Mitigated via:
  - Dropout layers (0.3)
  - Early stopping (patience=10)
  - Gradient clipping (clipvalue=0.5)

2. ARIMA balanced speed and accuracy, ideal for:
  - Scenarios requiring rapid re-training
  - Baseline comparisons

3. Prophet provided intuitive seasonality insights but lagged in accuracy due to:
  - Bitcoin’s non-stationary behavior
  - Limited exogenous variable support

### Future Work 

**1. For Practitioners**

- **Traders:** Use LSTM + ARIMA hybrids for precision and speed.
- **Analysts:** Leverage Prophet for trend decomposition and risk intervals.

**2. Improvements**

- **Data Enrichment:** Add trading volume, Google Trends, or macroeconomic indicators.
- **Hybrid Models:** Combine ARIMA’s residuals with LSTM (e.g., ARIMA-LSTM).
- **Real-Time API:** Deploy models with FastAPI for live predictions.

### Source

![Bitcoin Historical Data from Kaggle](https://www.kaggle.com/datasets/mczielinski/bitcoin-historical-data)
