#  Time Series Forecasting of Stock Prices using ARIMA and LSTM

##  Project Overview
Time series forecasting is a key technique in data science, especially in finance, where predicting future trends supports decision-making and risk management.  
This project predicts **daily stock closing prices** using both **classical statistical methods** and **deep learning**.

We compare:
- **Naive Baseline**
- **ARIMA (5,1,0)**
- **LSTM**

>  Educational project only. Not financial advice.

---

##  Real-World Problem
Stock prices follow complex patterns driven by trends, volatility, and external events.  
Forecasting helps in:
- Trend monitoring  
- Risk awareness  
- Building decision-support tools  

However, financial time series are noisy and often non-stationary, making forecasting challenging.

---

##  Solution Approach (Pipeline)
1. Download real stock data (Apple: AAPL) from a public source
2. Preprocess and visualize the time series
3. Split data using time-aware train/test split
4. Train multiple models (baseline, ARIMA, LSTM)
5. Evaluate using MAE, RMSE, and MAPE
6. Forecast the next 30 days using the LSTM model

---

##  Dataset
- **Source:** Stooq (public dataset)
- **Company:** Apple Inc. (AAPL)
- **Frequency:** Daily
- **Target:** Closing Price

---

##  Technologies Used
- Python
- NumPy, Pandas
- Matplotlib
- Scikit-learn
- Statsmodels (ARIMA)
- TensorFlow / Keras (LSTM)
- Google Colab

---

## Models Implemented

### Naive Baseline
- Predicts the next value as the previous day’s closing price.
- Used as a strong benchmark for time series.

### ARIMA (5,1,0)
- Classical statistical forecasting model.
- Works best when the series is stationary and parameters are well-tuned.

### LSTM
- Deep learning model designed for sequential data.
- Uses a sliding lookback window to learn temporal patterns.

---

##  Evaluation Metrics
Models are evaluated on the **last 20%** of the dataset using:
- **MAE** (Mean Absolute Error)
- **RMSE** (Root Mean Squared Error)
- **MAPE** (Mean Absolute Percentage Error)

---

## Results 
| Model | MAE | RMSE | MAPE |
|------|-----:|-----:|-----:|
| Naive Baseline | **1.6912** | **2.5885** | **1.33%** |
| ARIMA(5,1,0) | 97.3231 | 118.9278 | 60.67% |
| LSTM | 44.5649 | 57.6084 | 26.56% |

###  Interpretation
- The **Naive Baseline performed best** on this dataset split because short-term stock prices often change gradually, making “yesterday = today” a very strong benchmark.
- **ARIMA performed poorly** here, likely due to non-stationarity, volatility, and parameter settings (ARIMA needs careful tuning and stationarity checks).
- **LSTM performed better than ARIMA**, but still did not beat the Naive Baseline in this run, showing how difficult stock forecasting is and why baselines matter.

---

##  Future Forecasting
After training, the LSTM model generates a **next 30-day forecast** using recursive prediction to demonstrate forward forecasting beyond the observed dataset.

---

##  Ethical Considerations
- Uses **public stock market data**
- No personal or sensitive data involved
- Not used for automated trading or real financial decision-making
- Limitations and uncertainty are clearly acknowledged

---

## 📁 Repository Structure
