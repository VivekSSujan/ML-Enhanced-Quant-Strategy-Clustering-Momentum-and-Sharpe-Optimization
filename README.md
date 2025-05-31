# ML-Enhanced-Quant-Strategy-Clustering-Momentum-and-Sharpe-Optimization
A machine learning–powered quantitative trading strategy using clustering, momentum signals, and portfolio optimization. Backtested on 8 years of S&amp;P 500 data with integrated Fama-French factors.

This project explores the use of machine learning and quantitative finance techniques to construct a dynamic trading strategy. The core idea is to use unsupervised learning to group similar stocks and apply financial theory to optimize a monthly-rebalanced portfolio that aims to outperform the S&P 500 benchmark.

---

## Project Highlights

- 8 years of historical stock data from the **S&P 500** sourced via Yahoo Finance
- Feature engineering using:
  - **Technical indicators** like RSI, ATR, MACD, Bollinger Bands
  - **Volatility metrics** such as Garman-Klass volatility and dollar volume
  - **Momentum & lagged returns** over multiple time horizons
  - **Fama-French 5-Factor** risk exposures via Rolling OLS
- Stock clustering using **K-Means** to detect patterns in behavior
- Monthly stock selection based on **cluster membership and RSI filter**
- Portfolio optimization using **PyPortfolioOpt’s Efficient Frontier** targeting maximum **Sharpe Ratio** with diversification constraints
- **Backtesting framework** for monthly rebalancing and daily return tracking
- Performance comparison against a passive **SPY Buy & Hold** strategy

---

## Strategy Logic

1. **Data Preparation**  
   Gather 8 years of S&P 500 price data and compute required features (RSI, ATR, Garman-Klass, returns, etc.).

2. **Clustering**  
   Use KMeans clustering to segment stocks into behaviorally similar groups.

3. **Stock Selection**  
   From a specific cluster, select stocks with RSI near 70 to exploit potential momentum.

4. **Portfolio Construction**  
   Use **Efficient Frontier optimization** to assign weights that maximize the Sharpe ratio, with stock weight constraints (min = 0.5×equal, max = 10%).

5. **Backtesting**  
   Rebalance monthly, compute daily returns, and compare the cumulative performance with SPY.

---

## 📚 For Beginners: I Documented My Learning Journey Too!

As someone completely new to finance, I asked myself **tons of questions** while building this project — from *“What is RSI?”* to *“How does RollingOLS actually work?”*

To help others who are just starting out, I’ve compiled all those questions and answers into a **Q&A-style learning document**. It’s included in the GitHub repo as:

📄 `Learnings_in_QnA_Format.pdf`  
✅ Great for self-study and grasping key financial concepts from scratch.

## Future Work

- Explore alternative clustering methods (e.g., DBSCAN, Hierarchical)
- Introduce risk-adjusted stock filtering (e.g., Beta neutrality)
- Deploy via Streamlit or Dash for interactive portfolio visualization

