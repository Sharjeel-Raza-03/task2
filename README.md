# Task 2: Predict Future Stock Prices Short-Term

## Overview

This project is part of the **DevelopersHub Corporation AI/ML Engineering Internship Tasks**.

The goal of this task is to use historical stock market data to predict the **next day's closing price** of a selected stock. The dataset is downloaded using the `yfinance` Python library, and machine learning regression models are trained to compare actual and predicted closing prices.

---

## Objective

Use historical stock data to predict the next day's closing price using machine learning regression models.

---

## Dataset

The dataset is fetched from **Yahoo Finance** using the `yfinance` Python library.

Example stock used:

```text
AAPL - Apple Inc.
```

Other possible stocks:

```text
TSLA  - Tesla
MSFT  - Microsoft
GOOGL - Google
AMZN  - Amazon
```

---

## Features Used

The following features are used to predict the next day's closing price:

| Feature | Description |
|---|---|
| Open | Opening price of the stock |
| High | Highest price during the trading day |
| Low | Lowest price during the trading day |
| Volume | Number of shares traded |

---

## Target Variable

A new target column is created:

```text
Next_Close
```

This column represents the next day's closing price and is created by shifting the `Close` column by one row.

---

## Models Applied

Two regression models are used:

1. **Linear Regression**
2. **Random Forest Regressor**

Linear Regression is used as a simple baseline model, while Random Forest is used to capture more complex, non-linear relationships in the data.

---

## Project Workflow

1. Import required libraries
2. Download stock data using `yfinance`
3. Inspect the dataset
4. Check and handle missing values
5. Create the `Next_Close` target column
6. Select features and target variable
7. Split the data chronologically into training and testing sets
8. Train Linear Regression model
9. Train Random Forest Regressor model
10. Evaluate both models
11. Plot actual vs predicted closing prices
12. Predict the next day's closing price

---

## Evaluation Metrics

The models are evaluated using:

| Metric | Meaning |
|---|---|
| MAE | Mean Absolute Error |
| RMSE | Root Mean Squared Error |
| R2 Score | Measures how well the model explains price variation |

---

## Visualizations

The notebook includes the following plots:

- Actual vs predicted closing prices using Linear Regression
- Actual vs predicted closing prices using Random Forest
- Combined comparison of actual and predicted prices
- Feature importance plot for Random Forest

---

## Requirements

Install the required libraries before running the notebook:

```bash
pip install yfinance pandas numpy matplotlib scikit-learn
```

---

## How to Run

1. Clone this repository:

```bash
git clone https://github.com/your-username/your-repository-name.git
```

2. Open the project folder:

```bash
cd your-repository-name
```

3. Install dependencies:

```bash
pip install yfinance pandas numpy matplotlib scikit-learn
```

4. Open Jupyter Notebook:

```bash
jupyter notebook
```

5. Run the Task 2 notebook cell by cell.

---

## Example Code Snippet

```python
import yfinance as yf

stock_symbol = "AAPL"
data = yf.download(stock_symbol, period="5y")

data["Next_Close"] = data["Close"].shift(-1)
data = data.dropna()

features = ["Open", "High", "Low", "Volume"]
X = data[features]
y = data["Next_Close"]
```

---

## Results and Findings

- Historical Apple stock data was successfully downloaded using `yfinance`.
- Open, High, Low, and Volume were used as input features.
- The next day's closing price was used as the prediction target.
- Linear Regression provided a simple baseline prediction.
- Random Forest Regressor was also trained for comparison.
- Actual vs predicted closing price plots helped visualize model performance.
- The project demonstrates basic time series handling and regression modeling.

---

## Important Note

This project is for **educational purposes only**.

Stock market prices are affected by many unpredictable factors such as news, market sentiment, economic events, and global conditions. Therefore, this model should **not** be used for real financial investment decisions.

---

## Author
Sharjeel Raza
AI/ML Engineering Intern  
DevelopersHub Corporation 
