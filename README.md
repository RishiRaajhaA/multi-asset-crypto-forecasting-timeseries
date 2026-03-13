# Multi-Asset Crypto Market Forecasting

![Python](https://img.shields.io/badge/Python-3.10-blue)
![TensorFlow](https://img.shields.io/badge/DeepLearning-TensorFlow-orange)
![Machine Learning](https://img.shields.io/badge/MachineLearning-ScikitLearn-green)
![Time Series](https://img.shields.io/badge/TimeSeries-ARIMA%20%7C%20LSTM-purple)
![License](https://img.shields.io/badge/License-Academic-lightgrey)

---

# Project Overview

This project implements a **comprehensive cryptocurrency forecasting framework** using classical statistical models, econometric models, and deep learning approaches.

The objective is to **forecast Bitcoin (BTC-USDT) prices and analyze volatility and cross-asset relationships** using multiple time series models.

The project evaluates:

- Price forecasting accuracy
- Directional prediction
- Volatility modelling
- Risk metrics (Value-at-Risk)

---

# Models Implemented

The project compares **six different models across three categories**.

### Classical Statistical Models

- ARIMA

### Multivariate Econometric Models

- VAR (Vector Autoregression)
- GARCH
- EGARCH
- GJR-GARCH

### Deep Learning Models

- LSTM
- Bidirectional LSTM
- GRU

---

# Project Pipeline

```
Crypto Market Data (Binance)
        │
        ▼
Data Cleaning & Preprocessing
        │
        ▼
Feature Engineering
(RSI, MACD, EMA ratio, Bollinger %B, ROC, Fear & Greed Index)
        │
        ▼
Stationarity Testing (ADF)
        │
        ▼
Train-Test Split (80/20)
        │
        ▼
Model Training
│        │        │
ARIMA   VAR     GARCH
│
LSTM / Bi-LSTM / GRU
        │
        ▼
Rolling One-Step Forecasting
        │
        ▼
Evaluation Metrics
(MAE, RMSE, MAPE, R², Directional Accuracy)
        │
        ▼
Risk Analysis
(Value-at-Risk, Expected Shortfall)
```

---

# Dataset

The dataset consists of **BTC-USDT trading data from Binance** along with additional cryptocurrencies used for multivariate analysis.

Assets used:

- BTC-USDT
- ETH-USDT
- BNB-USDT
- SOL-USDT
- ADA-USDT

Dataset source:

Binance Historical Data  
https://www.binance.com/en/landing/data

Alternative dataset source:

https://www.kaggle.com/datasets

Example BTC dataset:

https://www.kaggle.com/datasets/mczielinski/bitcoin-historical-data

Fear & Greed Index:

https://alternative.me/crypto/fear-and-greed-index/

---

# Features Used

The deep learning models use **nine engineered features**:

| Feature | Description |
|------|-------------|
| Log Return | Price return transformation |
| Rolling Volatility | 42-period volatility |
| RSI | Relative Strength Index |
| Log Volume | Trading volume |
| EMA Ratio | Exponential Moving Average crossover |
| MACD Histogram | Trend momentum |
| Bollinger %B | Price position in Bollinger Bands |
| Rate of Change | Momentum indicator |
| Fear & Greed Index | Market sentiment indicator |

---

# Evaluation Metrics

Models were evaluated using:

| Metric | Description |
|------|-------------|
| MAE | Mean Absolute Error |
| RMSE | Root Mean Squared Error |
| MAPE | Mean Absolute Percentage Error |
| R² | Explained variance |
| Directional Accuracy | Correct price direction |
| F1 Score | Precision-recall balance |

---

# Results

## Price Forecasting Performance

| Model | MAE ($) | RMSE ($) | MAPE (%) | R² |
|------|--------|--------|--------|--------|
| ARIMA | 490.32 | 763.21 | 2.35 | 0.919 |
| LSTM | 188.79 | 275.16 | 0.91 | 0.989 |
| Bi-LSTM | **187.60** | 277.67 | **0.90** | **0.9893** |
| GRU | 247.71 | 352.00 | 1.20 | 0.982 |

---

## Directional Prediction Accuracy

| Model | Accuracy (%) | F1 Score |
|------|-------------|---------|
| ARIMA | 53.3 | 45.4 |
| LSTM | **78.8** | 75.5 |
| Bi-LSTM | **78.8** | 75.5 |
| GRU | **78.8** | **75.9** |
| VAR | 44.8 | 55.2 |
| GARCH | 32.3 | 5.1 |

---

# Key Findings

- Deep learning models outperform ARIMA in **price-level forecasting**
- **GRU performs comparably to LSTM with fewer parameters**
- Directional prediction accuracy remains around **50-55%**, consistent with the **Efficient Market Hypothesis**
- **GARCH models provide reliable volatility estimation**
- **VAR captures cross-asset relationships among cryptocurrencies**

---

# Technologies Used

### Programming Language

Python

### Libraries

- pandas
- numpy
- matplotlib
- seaborn
- statsmodels
- arch
- scikit-learn
- TensorFlow
- Keras

---

# Installation

Clone the repository

```bash
git clone https://github.com/RishiRaajhaA/multi-asset-crypto-forecasting-timeseries.git
cd multi-asset-crypto-forecasting-timeseries
```

Install dependencies

```bash
pip install pandas numpy matplotlib seaborn statsmodels arch scikit-learn tensorflow
```

Run Jupyter Notebook

```bash
jupyter notebook
```

Open the notebook:

```
BTC_USDT_TSA_Project.ipynb
```

---

# Project Structure

```
crypto-forecasting/
│
├── BTC_USDT_TSA_Project.ipynb
├── report.pdf
├── README.md
```

---

# Authors

Rishi Raajha A  
Naveen Sankar RS  
Sakthi Pranav S  
Harshvardhan V  

Amrita School of Artificial Intelligence  
Amrita Vishwa Vidyapeetham

---

# License

This project is intended for **academic and research purposes**.
