# 📈 Stock Price Prediction with Sentiment Analysis  
### LSTM + Financial News (TextBlob)

---

## 🧠 Overview

This project explores **stock price forecasting using deep learning combined with financial news sentiment analysis**.

The goal is to study whether **news sentiment can improve stock price prediction** when used alongside historical price data.

The project focuses on:
- Financial data cleaning  
- Sentiment analysis using TextBlob  
- LSTM time-series modeling  
- Single-ticker modeling for stability  

> This is an educational and research-focused project, not a trading system.

---

## 🎯 Objectives

- Clean and preprocess real-world financial data  
- Extract sentiment from news headlines  
- Train LSTM models on stock prices  
- Enhance LSTM using sentiment features  
- Compare price-only vs sentiment-enhanced models  
- Understand interaction between news and price movement  

---

## 📂 Dataset

### 📰 Financial News Dataset
Contains:
- Headline text  
- Date  
- Stock ticker  

Represents information such as:
- Analyst ratings  
- Earnings commentary  
- Market updates  

---

### 💲 Stock Price Data
Downloaded using **Yahoo Finance (yfinance)**:
- Date  
- Closing price  
- Ticker  

Closing prices are used because they represent end-of-day consensus value.

---

## 🧹 Data Cleaning (WiDS-Style Workflow)

Real financial data is messy. Cleaning steps include:

### ✔ Date Alignment
- Convert timestamps to date-only format  
- Align news with trading days  

---

### ✔ Missing Price Handling
- Markets closed on weekends/holidays  
- Forward-fill last available close  

---

### ✔ Ticker Cleaning
- Remove invalid/delisted tickers  
- Standardize ticker formats  

---

### ✔ Ticker Selection
Some tickers had very few headlines.

To ensure reliable modeling:
- Use the **most frequent ticker**
- Provides longer sequences  
- Reduces imbalance and noise  

---

## 💬 Sentiment Analysis

Sentiment is computed using **TextBlob**.

### Process
- Each headline gets polarity score  
- Range: `-1` (negative) to `+1` (positive)  
- Daily sentiment is averaged  

This produces a **daily sentiment signal**.

---

## 🤖 Model — LSTM

LSTM is chosen because it:
- Handles sequential data  
- Remembers long-term patterns  
- Captures nonlinear behavior  

---

### 🔑 LSTM Gates (Conceptual)
- **Forget Gate** → removes irrelevant info  
- **Input Gate** → stores useful info  
- **Output Gate** → controls prediction  

---

## 🧩 Modeling Strategy

### 📌 Model 1 — Price Only
Uses:
- Historical closing prices  
- Sliding window sequences  

Learns pure numerical trends.

---

### 📌 Model 2 — Price + Sentiment
Uses:
- Price sequences  
- Sentiment scores as extra feature  

Learns from:
- Market behavior  
- News mood  

---

## 📊 Evaluation Metrics

- RMSE (Root Mean Squared Error)  
- MAE (Mean Absolute Error)

Both models are tested on identical time periods.

---

## ❓ Why Single Ticker?

Using many tickers introduces:
- Sector variation  
- Data imbalance  
- Higher complexity  
- Harder interpretation  

Using one frequent ticker:
- Provides stable sequences  
- Isolates sentiment impact  
- Simplifies analysis  

---

## 🛠️ Tech Stack

- Python  
- Pandas  
- NumPy  
- yfinance  
- TextBlob  
- Pytorch 
- Matplotlib  

---

## 📈 Key Learnings

- Financial data cleaning is critical  
- Sentiment helps but isn't magic  
- LSTM captures trends better than classical models  
- Markets remain noisy and unpredictable  
- Simpler models often generalize better  

---

## 🚀 Future Improvements

- Finance-specific NLP (FinBERT)  
- Add macroeconomic indicators  
- Multi-ticker portfolio models  
- Transformer-based architectures  

---

## ▶️ How to Run

```bash
# Clone repository
git clone https://github.com/yourusername/yourrepo.git

# Install dependencies
pip install -r requirements.txt

# Run notebook/script
