# MLB Win Prediction: 10 Runs = 1 Win?

A Python project that predicts 2025 MLB team wins from run differential, built with pandas, scikit-learn, statsmodels, matplotlib, and seaborn.

**Full write-up:** [10 Runs = 1 Win: What a Regression Model Says](https://jacksonamrobeson.blogspot.com/2026/10/10-runs-1-win-what-regression-model.html)

## Key Finding

A single-variable linear regression on **run differential** (runs scored minus runs allowed) predicts team wins with a **5-fold cross-validated R² of about 0.80**. Run differential correlates with wins at 0.93, while team OPS has a weaker correlation of 0.64 (on a scale where 1.0 is a perfect match). Adding OPS as a second predictor did not improve the model, which I explored further with a formal multicollinearity check (VIF).

| Metric | Result |
|---|---|
| Correlation: wins vs. run differential | 0.93 |
| Cross-validated R² (5-fold) | 0.80 |
| VIF, run differential and OPS | about 1.6 each |

## What's in the Notebook

- Web scraping with error handling and retry logic
- Data cleaning (dtype fixes, merging, deduplication)
- Feature engineering, correlation analysis, and visualization
- Train/test split, linear regression, and residual analysis
- Multi-variable regression, VIF, and 5-fold cross-validation

## Limitations

- One season (2025) and 30 teams, so the sample is small and fold-to-fold results vary.
- Linear regression only; I did not compare other model types.

## How to Run

1. Download this repository.
2. Install the dependencies:
```
   pip install pandas numpy matplotlib seaborn scikit-learn statsmodels pybaseball
```
3. Open `mlb_win_prediction.ipynb` in Jupyter and choose **Kernel → Restart Kernel and Run All Cells**.

Data is pulled live from the web, so results may differ slightly if the source tables change.

## Author

Jackson Robeson | [Blog](https://jacksonamrobeson.blogspot.com)
