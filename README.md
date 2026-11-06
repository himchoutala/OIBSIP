# Data Analytics · Level 1 · Task 1 — EDA on Retail Sales Data

**Oasis Infobyte Internship Program (OIBSIP)** · Track: Data Analytics

## Objective
Perform a thorough Exploratory Data Analysis on a retail sales dataset to uncover sales patterns, customer behaviour and actionable business insights.

## Files
| File | Description |
|---|---|
| `Task1_EDA_Retail_Sales.ipynb` | Full EDA notebook with written observations after each chart |
| `retail_sales_data.csv` | Dataset: 3,893 transactions, Jan 2023 – Dec 2024 |
| `screenshots/` | Exported charts |

## Tech Stack
Python · pandas · numpy · matplotlib · seaborn · Jupyter Notebook

## What the notebook covers
- Initial inspection (shape, dtypes, nulls, duplicates)
- Descriptive statistics (mean, median, mode, std)
- Monthly and quarterly sales trends
- Customer demographics (age groups, gender)
- Top 10 products (by units and by revenue); revenue by category
- Correlation heatmap
- Extra insights: discount effectiveness, category mix by age group, weekday revenue
- Conclusion with business recommendations

## Key findings
- **Strong seasonality:** Q4 brings ~36% of revenue; Dec 2024 was the peak month.
- **Weekends:** Saturday + Sunday generate ~35% of revenue.
- **Electronics** earns ~48% of revenue from ~13% of units; **Clothing** is the volume driver.
- **Discounts don't lift order size:** average quantity stays ~2.0 from 0% to 30% off, while revenue per order falls ~35%.
- **Age shapes *what* is bought**, not *how much*: Clothing for 18–25, Home & Kitchen for 56+.

## Recommendations
1. Replace blanket deep discounts with targeted offers and A/B test them.
2. Plan stock, staffing and ad spend around Q4 and weekends.
3. Use Clothing to bring in traffic and cross-sell Electronics accessories.
4. Target campaigns by age group.
5. Build a loyalty programme for the top 10% of customers (~25% of revenue).

## How to run
```bash
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook Task1_EDA_Retail_Sales.ipynb
```

## Note
The dataset is synthetic, generated for this analysis. The notebook runs unchanged on any retail dataset with the same columns.
