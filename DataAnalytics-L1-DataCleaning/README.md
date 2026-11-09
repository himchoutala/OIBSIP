# Data Analytics · Level 1 · Task 3 — Cleaning Data

**Oasis Infobyte Internship Program (OIBSIP)** · Track: Data Analytics

## Objective
Take a deliberately messy customer-orders dataset and turn it into a clean, analysis-ready dataset, documenting every decision.

## Files
| File | Description |
|---|---|
| `Task3_Data_Cleaning.ipynb` | Full cleaning workflow with markdown justifications |
| `messy_customer_orders.csv` | Raw (synthetic) dataset with deliberate data-quality problems |
| `cleaned_customer_orders.csv` | Output produced by running the notebook |
| `screenshots/` | Key outputs and charts |

## Tech Stack
Python · pandas · numpy · matplotlib · seaborn · Jupyter Notebook

## Problems in the raw data
- Duplicate rows
- Nulls in several columns
- Inconsistent labels (`M` / `male` / `Female`, `CC` / `Credit Card`, `Bangalore` / `Bengaluru`)
- Three different date formats stored as text
- Currency symbols (`$1,234.50`) inside numeric columns
- Impossible ages (negative, 250, 999)
- Extreme order amounts

## Approach
1. **Data quality report** — nulls, duplicates, dtypes, range anomalies
2. **Duplicate removal** — exact duplicates dropped (first kept)
3. **Standardisation** — whitespace, case, and label mapping
4. **Type correction** — ID → string, dates → datetime, money → float
5. **Outliers** — impossible ages set to NaN; order amounts capped using the IQR method
6. **Missing values** — median (age, amount, rating), mode (quantity), "Unknown" (gender, city), row drop (missing date); each choice justified in the notebook
7. **Before vs. after summary** and export of the cleaned CSV

## Results
| Metric | Before | After |
|---|---|---|
| Rows | 1,050 | 978 |
| Null cells | 398 | 0 |
| Duplicate rows | 50 | 0 |
| Columns with correct dtype | 7/10 | 10/10 |

## How to run
```bash
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook Task3_Data_Cleaning.ipynb
```
Run all cells; `cleaned_customer_orders.csv` is saved next to the notebook.

## Note
The dataset is synthetic, generated to contain realistic data-quality problems.

## Demo
- Demo video / LinkedIn post: [paste your link here]
