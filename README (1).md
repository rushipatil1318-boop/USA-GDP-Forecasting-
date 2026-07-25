# US Real GDP Growth — Time Series Forecasting

**Course:** Simulation & Forecasting Techniques — ISM International School of Management, Dortmund
**Data:** World Bank (`NY.GDP.MKTP.KD.ZG`) — Annual Real GDP Growth, USA, 1961–2025
**Benchmark:** IMF World Economic Outlook (WEO), April 2026

## Overview

This project builds and evaluates **11 classical time series forecasting models** on 64 years of US real GDP growth data, runs a rolling-origin backtest to measure genuine out-of-sample accuracy, combines the two strongest models, and benchmarks every forecast against the IMF's official 2026–2030 projections.

## What's inside

| Step | Description |
|------|-------------|
| 1 | Exploratory analysis of the GDP growth series (trend, seasonality-style decomposition, distribution) |
| 2 | Stationarity testing with the Augmented Dickey-Fuller (ADF) test across differencing levels |
| 3 | Fitting all 11 models: Mean, MA(3), MA(5), WMA(3), WMA(5), SES, Holt Damped, Linear Regression, ARIMA, Holt-Winters, and a Combination model |
| 4 | Residual diagnostics — Ljung-Box (white noise) and Shapiro-Wilk (normality) tests for every model |
| 5 | Forecast combination (Bates & Granger, 1969) — equal-weighted blend of ARIMA and Holt-Winters |
| 6–7 | Forward forecasts for 2026–2030 plotted against IMF WEO projections |
| 8 | Rolling-origin out-of-sample backtest and model accuracy leaderboard (MAE, RMSE) |
| 9 | Comprehensive 4-panel comparison of all 11 models vs. IMF WEO (bias, MAE/RMSE, trend slope) |

## Key methods

- **Models:** Mean, Moving Averages (simple & weighted), Simple Exponential Smoothing, Damped Holt, Linear Regression, ARIMA, Holt-Winters, and an equal-weight ARIMA + Holt-Winters combination
- **Validation:** Rolling-origin (walk-forward) backtesting — no future data leakage
- **Diagnostics:** Ljung-Box test for residual autocorrelation, Shapiro-Wilk test for normality
- **Benchmarking:** All forecasts compared against IMF WEO April 2026 projections on bias, MAE, RMSE, and trend slope

## Tech stack

- Python 3
- `pandas`, `numpy` — data handling
- `statsmodels` — ARIMA, Holt-Winters, ADF test, Ljung-Box test, seasonal decomposition
- `scikit-learn` — accuracy metrics
- `scipy` — Shapiro-Wilk test
- `matplotlib` — visualization

## How to run

```bash
pip install -r requirements.txt
jupyter notebook USA_GDP_FINAL.ipynb
```

## Results snapshot

The notebook identifies the best-performing individual model and the ARIMA + Holt-Winters combination via out-of-sample RMSE, then shows how closely each 2026–2030 forecast path tracks the IMF WEO's projected gentle deceleration in US growth. See the notebook for the full leaderboard and comparison charts.

## Author

Rushikesh — MSc Business Intelligence & Data Science, ISM Dortmund

---
*This project was completed as part of coursework and is shared for portfolio purposes.*
