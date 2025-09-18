# Time-Series-Analysis-Stock-Closing-Prices-
This repository contains my **Level 2 Task 2 (Intermediate)** from the **Data Analysis Internship at Codveda Technologies**. 

# 📈 Time Series Analysis – Stock Closing Prices  

This repository contains my **Level 2 Task 2 (Intermediate)** from the **Data Analysis Internship at Codveda Technologies**.  

The project demonstrates **time series forecasting** on stock closing prices using **ARIMA, SARIMA, and SARIMAX** models.  

---

## 🎯 Objective  
The goal of this project is to analyze a stock time-series dataset to detect **trends, seasonality, and residuals**, and extend it with **forecasting models**.  

Specifically, the task involved:  
- Plotting stock time series and identifying **patterns**.  
- Decomposing the series into **trend, seasonality, and residuals**.  
- Applying **moving average smoothing**.  
- Running **stationarity tests (ADF)** and differencing if required.  
- Using **ACF & PACF plots** to identify ARIMA orders.  
- Forecasting with **ARIMA, SARIMA, and SARIMAX**.  
- Comparing model results and providing **business insights**.  

---

## 🗂 Dataset  

The dataset contains **daily stock prices** for multiple companies.  

| Column   | Description |
|----------|-------------|
| symbol   | Stock ticker symbol (e.g., AAPL, AAL, ACN) |
| date     | Date of observation |
| open     | Opening price |
| high     | Highest price |
| low      | Lowest price |
| close    | Closing price (focus of analysis) |
| volume   | Trading volume |

---

## 🔎 Workflow  

### Step 1 – Import Libraries  
Loaded essential Python libraries: pandas, matplotlib, seaborn, statsmodels.  

### Step 2 – Load & Explore Dataset  
Inspected stock dataset, confirmed structure, and indexed by date.  

### Step 3 – Preprocess Data  
- Generic filter using `symbol_choice`.  
- Focused on **closing price** (primary variable).  

### Step 4 – Plot Time Series  
Visualized raw stock closing prices.  

### Step 5 – Decomposition  
Separated series into **trend, seasonality, residuals** using `seasonal_decompose`.  

### Step 6 – Moving Average Smoothing  
Applied **30-day** and **90-day moving averages**.  

### Step 7 – Stationarity Check (ADF Test)  
Confirmed non-stationarity, then applied differencing.  

### Step 8 – Differencing  
First-order differencing made the series **stationary**.  

### Step 9 – ACF & PACF Analysis  
Identified likely ARIMA(1,1,1) model.  

### Step 10 – ARIMA  
Baseline forecasting → weak fit (negative R²).  

### Step 11 – SARIMA  
Modeled seasonality → improved interpretability.  

### Step 12 – SARIMAX  
Added **Volume** as an exogenous variable → more realistic market-aware forecasts.  

### Step 13 – Model Comparison  
Compared ARIMA, SARIMA, SARIMAX.  

### Step 14 – Conclusion  
Confirmed objectives achieved: patterns detected, decomposition done, smoothing applied, stationarity tested, forecasts generated.  

### Step 15 – Business Interpretation & Insights  
Translated technical results into practical insights for **traders, portfolio managers, and corporates**.  

---

## 📊 Results  

### Model Performance  
| Model   | Mean Squared Error | R² Score |
|---------|---------------------|----------|
| ARIMA   | 383.95              | -2.41    |
| SARIMA  | 133.36              | -0.19    |
| SARIMAX | 135.98              | -0.21    |

📌 **Observation:**  
- ARIMA alone → poor fit, misses seasonality.  
- SARIMA → captures trend + cycles.  
- SARIMAX → integrates exogenous factors (volume), but requires stronger external predictors.  

---

## 💼 Business Insights  

- **Traders:** ARIMA useful for short-term momentum, SARIMA helps align with quarterly cycles.  
- **Portfolio Managers:** SARIMA forecasts support medium-term allocation decisions.  
- **Risk Managers:** SARIMAX highlights how **trading activity** influences volatility.  
- **Corporates:** Provides confidence in planning & hedging strategies.  

✅ **Key Takeaway:** SARIMA and SARIMAX outperform ARIMA in financial forecasting.  

---

## ⚙️ Requirements  

```txt
pandas
numpy
matplotlib
seaborn
statsmodels
scikit-learn
pip install -r requirements.txt
```

# 📂 **Repository Structure**

Time-Series-Stock-Analysis/
│
├── data/
│   └── stocks.csv                # Raw dataset (daily stock prices)
│
├── notebooks/
│   └── Time Series Analysis - Stock Closing Prices.ipynb   # Full notebook
│
├── images/                       # Exported plots for README
│   ├── timeseries_plot.png
│   ├── decomposition.png
│   ├── moving_average.png
│   ├── acf_pacf.png
│   ├── arima_fit.png
│   ├── sarima_fit.png
│   ├── sarimax_fit.png
│
├── README.md                     # Main project documentation
└── requirements.txt              # Python dependencies
