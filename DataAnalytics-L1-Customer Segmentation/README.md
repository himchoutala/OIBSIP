# Data Analytics · Level 1 · Task 2 — Customer Segmentation Analysis

**Oasis Infobyte Internship Program (OIBSIP)** · Track: Data Analytics

## Objective
Use K-Means clustering to split a company's customers into distinct groups that can be targeted with different marketing strategies.

## Dataset
*Customer Segmentation* (`Train.csv`): 8,068 customers of an automobile company, with demographics, work profile and a `Spending_Score` (Low / Average / High). The file also contains the company's own labels (A/B/C/D), which are **not** used for clustering.

> **Important — difference from the task brief:** the brief suggests RFM analysis (Recency, Frequency, Monetary). This dataset has **no transaction history**, so RFM, average purchase value, purchase frequency and customer lifetime value **could not be calculated** and were not invented. I clustered on `Age`, `Work_Experience`, `Family_Size` and `Spending_Score` (the closest available proxy for the monetary dimension). A full RFM version needs a transaction dataset such as UCI *Online Retail*.

## Files
| File | Description |
|---|---|
| `Task2_Customer_Segmentation.ipynb` | Full analysis with written observations |
| `Train.csv` | Dataset |
| `screenshots/` | Exported charts |

`Test.csv` was not used: it has no labels, and 2,332 of its 2,627 IDs also appear in `Train.csv`, so combining the files would double-count customers.

## Tech Stack
Python · pandas · numpy · scikit-learn (KMeans, StandardScaler, PCA) · matplotlib · seaborn · Jupyter Notebook

## Approach
1. Inspect structure and missing values
2. Clean data: 163 impossible `Work_Experience` values capped at `Age − 16`; median / mode / "Unknown" imputation, each justified
3. Descriptive statistics and distributions
4. Feature selection (4 features) and `StandardScaler`
5. **Elbow method + silhouette score** to choose K (K = 5)
6. K-Means; cluster scatter plots (Age vs Family Size, Age vs Work Experience, PCA view)
7. Cluster profiles, bar chart of customers per cluster
8. Comparison with the company's A–D labels; marketing recommendation per segment

## Results — five segments
| Segment | Size | Avg age | Profile | Spending |
|---|---|---|---|---|
| Young Starters | 24% | 27 | Mostly unmarried, large households (≈4) | 99% Low |
| Experienced Professionals | 18% | 38 | ≈8 years of work experience | mixed (69% Low) |
| Settled Families | 24% | 45 | Married, ≈3.5 people | 74% Average, 26% High |
| Frugal Small Households | 24% | 50 | Small households (≈1.6) | 100% Low |
| Affluent Seniors | 10% | 71 | Married, oldest group | 79% High |

## Evaluation (honest summary)
- Silhouette at K = 5: **0.325** (moderate; segments overlap).
- Clusters are **stable**: agreement between random restarts ≥ 0.996.
- Agreement with the company's A–D labels is **low** (adjusted Rand index 0.085), so these segments are a complementary view, not a replacement.
- Recommendations (e.g. premium, high-touch retention for Affluent Seniors; entry-level and financing offers for Young Starters) are hypotheses that need pilot testing.

## How to run
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook Task2_Customer_Segmentation.ipynb
```

## Demo
- Demo video / LinkedIn post: [paste your link here]
