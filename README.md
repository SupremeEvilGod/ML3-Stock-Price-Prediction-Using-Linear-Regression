---

# Stock Price Prediction Using Linear Regression

## Overview

This project demonstrates how to use **Linear Regression** to predict stock market **Close Prices** based on **Open Prices** using real-time stock data. The model is built using the **scikit-learn** library and evaluates its performance using common metrics like **Mean Squared Error (MSE)** and **R-squared**. A visualization of the regression line along with actual data points is also provided.


## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Visualization](#visualization)

## Dataset

The dataset is fetched in real-time from stock data APIs (like Yahoo Finance/Alpha Vantage API/IEX Cloud API) and contains the following columns:

- **Datetime:** Timestamp of the stock price
- **Open:** Opening price of the stock
- **High:** Highest price during the minute
- **Low:** Lowest price during the minute
- **Close:** Closing price of the stock at the end of the minute
- **Adj Close:** Adjusted closing price
- **Volume:** Volume of trades during the minute

We focus on predicting the `Close` price using the `Open` price.

## Technologies Used

- **Python** (v3.8 or later)
- **Pandas** (for data manipulation)
- **Matplotlib** (for data visualization)
- **Scikit-learn** (for building the Linear Regression model)
- **YahooFinance API** (for fetching real-time stock data)

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/SupremeEvilGod/ML3-Stock-Price-Prediction-Using-Linear-Regression.git
cd ML3-Stock-Price-Prediction-Using-Linear-Regression
```

### 2. Install Dependencies

Make sure you have Python installed. Then, install the required libraries using `pip`.

```bash
pip install -r requirements.txt
```

The `requirements.txt` file includes:
```txt
numpy
pandas
scikit-learn
matplotlib
yfinance
```

### 3. Fetch Real-Time Stock Data

You can modify the script to fetch data for your preferred stock ticker using the `yfinance` library.

```python
import yfinance as yf

# Fetch data for a specific stock (e.g., MSFT)
data = yf.download(tickers="MSFT", period="1d", interval="1m")
```

## Usage

1. **Run the Model:**

   You can execute the Python script or Jupyter notebook to fetch the stock data, build the Linear Regression model, and evaluate its performance.

2. **Model Outputs:**
   - **Model Coefficient (Slope)**: How much the `Close Price` changes with respect to `Open Price`.
   - **Model Intercept**: Where the regression line intercepts the y-axis.
   - **Mean Squared Error (MSE)**: A measure of the model's error (lower is better).
   - **R-squared Value**: Indicates how well the model explains the variance in the data.

## Results

- **Model Coefficients:**
  - Coefficient (Slope): `0.971`
  - Intercept: `6.313`

- **Performance Metrics:**
  - Mean Squared Error (MSE): `0.0148`
  - R-squared: `0.977`

These metrics show that the model performs very well, with 97.7% of the variance in the `Close Price` explained by the `Open Price`.

## Visualization

The scatter plot below shows the actual data points (in blue) and the predicted regression line (in red).

![image](https://github.com/user-attachments/assets/7eb9d0d6-9f0a-40e5-802c-2b0658a740ce)

