
# Stock Market Signal Prediction

## Overview
This project explores whether machine learning can support better investment decisions by predicting short-term stock price movements. By analyzing over 14 years of Tesla (TSLA) daily stock data, we developed a binary classifier to identify "Up Opportunities" — days when stock returns are likely to exceed a predefined threshold. The ultimate goal is to support retail investors in improving market timing strategies.

Prepared by: Vy Nguyen, Dennis Wu, Kenjee Koh, Hsiang-Han Huang, Becky Wang

Key results include:
- Gradient Boosting model achieved 59.03% accuracy on unseen data
- Feature importance analysis showed MA Ratio, Volatility, and RSI were key predictors
- A scenario simulation projected a 393% annual return under specific trading assumptions

## Dataset
- **Source:** yfinance Python library
- **Scope:** 14+ years of Tesla (TSLA) daily data (2009–2023)
- **Size:** 3,632 records (reduced to 3,577 after preprocessing)
- **Key Features:** MA Ratio, RSI, Volatility, Volume Change, Day of Week, and Signal (target)

## Tools & Methodology Overview
**Languages and Libraries:** Python (pandas, numpy, scikit-learn, matplotlib, seaborn)

### Data Processing:
- Downloaded historical TSLA data using `yfinance` (3632 records)
- Engineered 6 technical indicators: MA Ratio, RSI, Volatility, Volume Change, Price Trend, and Day of Week
- Created a binary target variable (`Signal`) to classify "Up Opportunity" days

### Exploratory Analysis:
- Analyzed class distribution (balanced: 44.8% Up vs 55.2% No Opportunity)
- Performed summary statistics and outlier checks
- Evaluated correlation and feature distributions

### Modeling Techniques:
- Trained Decision Tree, Random Forest, and Gradient Boosting models
- Applied RandomizedSearchCV and TimeSeriesSplit (5 folds) for hyperparameter tuning
- Tested two data-splitting strategies: random and chronological

### Evaluation Metrics:
- Accuracy, Precision, Recall, F1-Score (overall and class-specific)
- Feature importance analysis
- Investment scenario simulation based on prediction results

## Highlighted Visualizations
**Feature Importance:**
![Feature Importance](Notebooks/feature_importance.png)

**Volume Change Boxplot:**
![Volume Boxplot](Notebooks/volume_boxplot.png)

**Volatility Trend (Monthly):**
![Volatility Trend](Notebooks/volatility_trend.png)

## Results & Key Insights
- **Gradient Boosting** with random split performed best (59.03% accuracy)
- **Chronological split** provided more realistic testing of future stock predictions
- **MA Ratio, Volatility, and RSI** were the most important features
- **Day-of-week** variable had negligible effect
- Scenario simulation showed high potential return with modest accuracy

## Key Deliverables
- Jupyter Notebook: `notebooks/Group_Project_Stock_Market_Signals_Team_12B.ipynb`
- Final project report (PDF)
- Visuals and scenario analysis summaries

## What I Learned
- Tree-based models are effective for technical signal classification but have clear limitations in financial time-series
- Predicting stock returns using classification is inherently difficult due to market noise, data biases, and unpredictability
- I learned that models like Gradient Boosting are not robust for capturing temporal patterns — incorporating time-aware models like LSTM may lead to better results
- Broader variables (macroeconomic, fundamental, and news data) are important but were not included in this version

## What I Plan to Improve
- Extend analysis to other stocks beyond TSLA to test generalizability
- Incorporate macroeconomic variables and financial ratios for fundamental insights
- Experiment with LSTM and RNN for sequential pattern recognition in time-series

## About Me
I’m Vy Nguyen and I’m currently pursuing my Master of Science in Business Analytics at UC Irvine. I’m passionate about analytics, investment research, and financial modeling. Connect with me on [LinkedIn](https://www.linkedin.com/in/vy-ngoc-lan-nguyen).
