# ARIMA Modelling of S&P 500 Time Series  

## 📌 Project Overview  
This repository contains an in-depth time series analysis of the **S&P 500 daily closing prices** from **January 1, 2000, to December 31, 2023**. The main objective is to apply **ARIMA (Auto-Regressive Integrated Moving Average)** models to predict future values of the stock market index. The study involves **data preprocessing, stationarity checks, model selection, residual diagnostics, and performance evaluation**.

## 📊 Dataset  
- The dataset was retrieved from **Yahoo Finance** using the `quantmod` package.  
- It consists of **daily closing prices** for the S&P 500 index over a span of 24 years.  
- A **log transformation** was applied to stabilize variance before model fitting.

## 📈 Methodology  
### **1. Data Preprocessing**  
- Retrieved stock data using `quantmod`.  
- Applied **log transformation** to reduce heteroscedasticity.  
- Checked for missing values.  

### **2. Stationarity Checks & Differencing**  
- **Augmented Dickey-Fuller (ADF) test** was conducted to check stationarity.  
- The test results showed that the series was **non-stationary** (p > 0.05).  
- **First-order differencing** was applied, making the series stationary.  

### **3. Model Identification**  
- Used **Autocorrelation Function (ACF)** and **Partial Autocorrelation Function (PACF)** plots.  
- Initial model selection: **ARIMA(1,1,1)**.  
- Used `auto.arima()` to optimize model selection.  

### **4. Model Fitting & Selection**  
- The best-selected model was **ARIMA(0,1,1)** with the lowest **AIC/BIC scores**.  
- Model equation:  
  \[
  Y_t = \theta_1 \varepsilon_{t-1} + \varepsilon_t
  \]
- The simpler model was chosen to prevent **overfitting**.

### **5. Residual Diagnostics**  
- Residuals were **independent** based on ACF plots.  
- **Ljung-Box test** showed some residual autocorrelation.  
- **Q-Q plots** indicated slight deviations from normality.

### **6. Performance Evaluation**  
- Models were trained and validated using **Root Mean Squared Error (RMSE)** and **Mean Absolute Error (MAE)**.  
- ARIMA(0,1,1) performed well with minimal errors compared to ARIMA(1,1,1).  
- Forecasts aligned closely with the validation set.

## 📌 Results  
- The **ARIMA(0,1,1) model** successfully captured trends in S&P 500 prices.  
- Some autocorrelation remained, suggesting the potential for additional refinements.  
- The model can be improved by incorporating **external economic indicators**.

## 🚀 Future Work  
- Exploring **exogenous variables (e.g., interest rates, inflation)** to improve model accuracy.  
- Trying **LSTM models** for deep learning-based time series forecasting.  
- Implementing **GARCH models** to better capture stock market volatility.

## 🛠️ Technologies Used  
- **Python** (pandas, statsmodels, numpy, matplotlib, seaborn)  
- **R** (for auto.arima() model selection)  
- **Jupyter Notebook** for analysis  
- **Git & GitHub** for version control   
## 👨‍💻 Author
Kaushal Gurung

🔗 GitHub: github.com/Kaushalgurung
