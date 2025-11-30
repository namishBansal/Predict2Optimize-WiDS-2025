# Predict2Optimize — WiDS 2025  
Predicting Market Dynamics for Data-Driven Portfolio Optimization

## Overview
You will build a simple pipeline that uses financial data to predict asset returns and construct a basic optimized portfolio. The project progresses step-by-step: data → features → prediction → optimization → backtesting.

---

# Week 1 — Intro to Data Science in Python through Financial Data and Feature Extraction
**Goals**
- Use NumPy, Pandas, and Matplotlib.
- Download daily price data for a small set of stocks.
- Compute daily returns and build a basic feature table.

**Tasks**
- Simple introductory tasks in basic data science libraries
- Read price data (e.g., from `yfinance`).
- Handle missing values.
- Compute log returns.
- Create simple rolling features (e.g., past 5-day return, 20-day volatility).
- Visualize prices and returns.

---

# Week 2 — Baseline and Regression-based Predictors
**Goals**
- Build simple models to predict next-day return from features.
- Compare several basic regressors.

**Tasks**
- Create a train/test split respecting time order.
- Implement:  
  - baseline (predict mean)  
  - linear regression or ridge regression  
  - optionally a tree-based model (e.g., XGBoost)
- Evaluate using standard regression metrics.

---

# Week 3 — Neural Network and Backtesting
**Goals**
- Train a small MLP on your features.
- Run predictions in a rolling, walk-forward fashion.

**Tasks**
- Build a small MLP using PyTorch.
- Train with standard settings (normalization, early stopping).
- Implement a simple walk-forward backtest:  
  train on past data → predict next period → move forward → repeat.

---

# Week 4 — Portfolio Optimization
**Goals**
- Use predicted returns and estimated covariance to compute portfolio weights.
- Understand and apply the basic Markowitz model.

**Tasks**
- Estimate covariance from returns.
- Formulate expected return and risk.
- Solve the Markowitz problem using a library (we'll try to use `cvxpy` and compare with PyPortfolioOpt as benchmark)
- Apply practical constraints such as long-only weights.
- Compare outputs using different covariance estimates.

---

# Week 5 — Integration and Final Backtest
**Goals**
- Combine your predictor with your optimizer.
- Backtest the strategy over time.
- Visualize the results.

**Tasks**
- For each period: predict returns → compute optimized weights → track portfolio value.
- Plot cumulative returns.
- Plot the efficient frontier for a chosen date.
- Write a short summary of results and limitations.
- Accumulate results and work in final report

---

# Setup
Install the following packages:
```
pip install numpy pandas matplotlib yfinance scikit-learn xgboost torch cvxpy pyportfolioopt
```

# References
- NumPy, Pandas, Matplotlib official docs
- Scikit-Learn documentation
- PyTorch quickstart
- [`cvxpy` documentation](https://www.cvxpy.org/tutorial/index.html) -- library for convex optimization solvers
- [PyPortfolioOpt documentation](https://pyportfolioopt.readthedocs.io/en/latest/) -- reference library for benchmarking
- [The Portfolio Optimization book](https://portfoliooptimizationbook.com/portfolio-optimization-book.pdf) -- Ch 1, 2, 3 (weeks 1-2); 6, 7, 8 (weeks 4-5) can be helpful
- [Successful Algorithmic Trading](https://raw.githubusercontent.com/englianhu/binary.com-interview-question/fcad2844d7f10c486f3601af9932f49973548e4b/reference/Successful%20Algorithmic%20Trading.pdf) -- general reference
- Paper: [Decision-Focused Learning:  Foundations, State of the Art,Benchmark and Future Opportunities, 2024, JAIR](https://www.jair.org/index.php/jair/article/view/15320/27076) -- Practical discussion on general 'Predict-to-Optimize' frameworks, with Page 40 framing the exact portfolio optimization problem
