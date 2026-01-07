Linear Programming Portfolio Backtester

📌 Project Overview
This project is a Python-based backtesting engine designed to automate portfolio construction using Linear Programming (LP).

The primary goal of this project is educational: to familiarize myself with portfolio optimization techniques, quantitative finance libraries, and the mechanics of building a rolling-window backtesting engine. It explores how mathematical optimization (maximizing returns) interacts with historical market data.

🛠 Tech Stack
Language: Python

Data Manipulation: Pandas, NumPy

Optimization: CVXPY (Convex Optimization)

Stock Data for testing: Yahoo Finance (however the api is sooo unreliable so I had to get the data by copy and pasting each stock's data one by one into Excel so I can get csv files)
Note to self: don't do that again for testing

Visualization: Matplotlib

⚙️ Key Features
Rolling Backtest Engine: Simulates a strategy that moves through time (e.g., 5-year history), re-optimizing the portfolio at set intervals (e.g., every 20 days).

Linear Optimization Strategy: Uses a "Greedy" LP solver to maximize expected returns based on a lookback window (e.g., past 60 days). 
Note: another reason this is purely for my learning since this is not a really refined model, it would essentially default the weight to 25% for each of the top 4 stocks each time rebalancing came around

Constraint Management: Enforces real-world rules like "Full Investment" (Sum of weights = 1.0) and "Diversification Caps" (Max weight per stock = 25%). 

Performance Visualization: Plots portfolio growth vs. individual stock performance and visualizes the "Ranking Race" of expected returns over time.

🚀 How It Works
Data Ingestion: Loads CSV data for selected tickers (e.g., XOM, TSLA, AAPL, MSFT, GOOG).

Rolling Window: The engine steps through time day-by-day.

Signal Generation: Every $N$ days (rebalance frequency), it looks back $X$ days to calculate expected returns.

Optimization: The CVXPY solver allocates capital to the top-performing assets while respecting weight limits.

Result: Outputs a time-series of total portfolio value and logs every rebalancing decision.


📉 Example Output
Rebalance Log: Shows exactly which stocks were bought/sold and their new weights.

Shadow Price Analysis: Identifies which constraints (e.g., "Max 25%") are actively limiting performance. (no surprise in the calculations since the model is purely profit driven, used to see if model is actually profit driven and because I wanted to)

Equity Curve: A visualization of how $100,000 would have grown using this strategy.

⚠️ Disclaimer
This project is for research and learning purposes only. The strategies implemented here use basic Linear Programming (maximizing past returns) and do not account for risk (volatility) or transaction costs. If you use my model for financial advice you lwk cooked gng
