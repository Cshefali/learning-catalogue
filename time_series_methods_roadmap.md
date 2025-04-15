# 🛣️ Time Series Learning Roadmap: From Zero to Pro

A step-by-step path to mastering time series analysis — from core stats to machine learning & deep learning — tailored for clarity, intuition, and real-world applications.

---

## 🌱 PHASE 1: Core Intuition + Classical Stats

Start here. These are the bread & butter of time series.

1. **What is a Time Series?**
   - Time dependency, temporal order, autocorrelation
   - Stationary vs non-stationary

2. **Visual Exploration**
   - Line plots, trend detection, seasonality
   - Rolling means, time-based splits

3. **Decomposition (STL)**
   - Trend + Seasonality + Residual
   - Additive vs Multiplicative

4. **AR, MA, ARMA**
   - Lag-based models
   - Autocorrelation Function (ACF) & Partial ACF (PACF)
   - When to use AR, when MA

5. **ARIMA**
   - Differencing (making data stationary)
   - Choosing (p, d, q)
   - Use `statsmodels` in Python

6. **SARIMA**
   - Handling seasonality (monthly sales, etc.)
   - Hyperparameter tuning (P, D, Q, s)

7. **ETS (Exponential Smoothing, Holt-Winters)**
   - Short-term forecasts
   - Smoothed values & decay rates

---

## 🛠️ PHASE 2: Applied Practice + Evaluation

8. **Model Evaluation**
   - Train-test split for time series (no shuffling!)
   - Metrics: MAE, RMSE, MAPE, sMAPE

9. **Cross-validation (Time Series Style)**
   - Walk-forward validation
   - Rolling-origin evaluation

10. **Business Use Cases**
    - Forecasting demand, sales, traffic, finance

---

## 🤹 PHASE 3: ML for Time Series (Feature-based)

11. **Feature Engineering**
    - Lag features, rolling stats (mean, std), date parts (month, day)
    - Fourier terms for seasonality

12. **Tree-based Models**
    - Random Forest, XGBoost, LightGBM on time series features
    - Handle missing data, non-linear patterns

13. **Anomaly Detection**
    - Z-score, isolation forest, rolling thresholds
    - Monitoring systems, fraud, sensor alerts

---

## 🧠 PHASE 4: Deep Learning for Sequences

14. **RNNs**
    - Basic idea of sequence models
    - Vanishing gradient problem

15. **LSTM & GRU**
    - Memory cells, gates
    - Long-range pattern modeling

16. **Autoencoders for Anomalies**
    - Learn typical patterns, flag what doesn’t match

---

## 🌀 PHASE 5: Advanced Time Series & Research Models

17. **Transformers for Time Series**
    - Self-attention
    - Used in forecasting, classification, anomaly detection

18. **Prophet (Facebook)**
    - Business use cases, holidays, events
    - Easy to tune, very popular

19. **VAR (Vector AutoRegression)**
    - Multivariate modeling
    - Granger causality, impulse response

20. **Wavelets & Fourier Transforms**
    - Detect complex cyclic/seasonal patterns
    - Used in EEG, seismic signals

---

## 🔁 PHASE 6: Real-World Integration

21. **Build Forecasting Dashboards**
    - Use Streamlit, Plotly Dash, or Flask
    - Let users select time range & model

22. **Deploy Time Series Models**
    - Save model, load in API or web app
    - Schedule predictions (daily/weekly)
