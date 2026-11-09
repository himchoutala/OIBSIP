# Data Analytics · Level 2 · Task 1 — Predicting House Prices with Linear Regression

**Oasis Infobyte Internship Program (OIBSIP)** · Track: Data Analytics

## Objective
Build and evaluate a linear regression model that predicts house prices from features such as number of rooms, building age and location-related variables.

## Dataset
Classic **Boston Housing** dataset (Harrison & Rubinfeld, 1978): 506 census tracts, 13 features, target `MEDV` (median home value in $1000s, 1970s prices). No header row; whitespace-separated.

## Files
| File | Description |
|---|---|
| `Task1_House_Price_Prediction.ipynb` | Full analysis with written observations |
| `housing.csv` | Dataset |
| `screenshots/` | Exported charts |

## Tech Stack
Python · pandas · numpy · scikit-learn · matplotlib · seaborn · Jupyter Notebook

## Approach
1. Inspect the data (no nulls or duplicates; 16 prices capped at 50)
2. Target distribution (right-skewed) and feature-selection discussion
3. One-hot encode `RAD` (accessibility index); drop `B` (see below)
4. Correlation heatmap
5. 80/20 train/test split; Linear Regression
6. Evaluate with MSE, RMSE, R²; 5-fold cross-validation
7. Actual-vs-predicted scatter, residual plots, coefficient analysis (raw and standardised)
8. **Bonus:** Ridge and Lasso comparison, plus a log-price experiment

## Results (test set)
| Model | R² | RMSE |
|---|---|---|
| Linear Regression | 0.684 | 4.81 |
| Ridge | 0.679 | 4.85 |
| Lasso | 0.684 | 4.82 |
| Linear on log(price) | **0.757** | **4.23** |

5-fold CV R² for Linear Regression: mean 0.717 (0.68–0.77 across folds).

## Key findings
- Strongest drivers: `LSTAT` (−), `RM` (+, about $4,080 per extra room), `DIS` (−), `NOX` (−), `PTRATIO` (−).
- **Residuals are not random:** a U-shaped pattern shows the relationship is partly non-linear; the model also produced one impossible negative price.
- **Ridge/Lasso do not help** (the model isn't overfitting); a **log-price** model does (R² 0.684 → 0.757).

## Ethical note and limitations
- The `B` column is derived from the proportion of Black residents in each tract, so I **excluded it** from the model. (scikit-learn removed this dataset for the same reason.) Performance is slightly better without it.
- This is 1970s Boston data and must not be used to value real homes today. `LSTAT` is also a socioeconomic proxy, so any real use would need a fairness review.

## How to run
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook Task1_House_Price_Prediction.ipynb
```

## Demo
- Demo video / LinkedIn post: [paste your link here]
