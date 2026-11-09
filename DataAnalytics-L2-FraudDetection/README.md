# Data Analytics · Level 2 · Task 3 — Fraud Detection

**Oasis Infobyte Internship Program (OIBSIP)** · Track: Data Analytics

> **Draft: fill in every [bracketed] item with your real results, and delete or edit any step you did not do.**

## Objective
Build a machine learning pipeline that detects fraudulent financial transactions in a heavily imbalanced dataset, treating class imbalance as the core challenge.

## Dataset
[Dataset name and source]: [number of transactions], of which [number] are fraudulent ([X]%). [Note if you used a sample of the full file.]

## Files
| File | Description |
|---|---|
| `[notebook name].ipynb` | Full analysis with written observations |
| `[data file]` | Dataset (or a note if it is too large to upload) |
| `screenshots/` | Exported charts |

## Tech Stack
Python · pandas · scikit-learn · imbalanced-learn · matplotlib / seaborn · Jupyter Notebook

## Approach
1. Analyse the class imbalance (percentage of fraud)
2. EDA: transaction amounts for fraud vs. non-fraud, time-of-day analysis
3. Explain why **accuracy is misleading** on imbalanced data
4. Handle the imbalance with [SMOTE / undersampling / `class_weight="balanced"`]
5. Stratified train/test split so fraud appears in both sets
6. Train [Logistic Regression] and [Random Forest / Decision Tree / XGBoost]
7. Evaluate with precision, recall, F1-score and ROC-AUC curve
8. Feature importance or coefficient analysis
9. Discussion of the recall vs. precision trade-off and of scalability

## Results (test set)
| Model | Precision | Recall | F1 | ROC-AUC |
|---|---|---|---|---|
| [Logistic Regression] | [ ] | [ ] | [ ] | [ ] |
| [Second model] | [ ] | [ ] | [ ] | [ ] |

## Key findings
- A model that always predicts "not fraud" would reach **[X]% accuracy** while catching **0 frauds**, which is why accuracy was not used.
- The most important metric is **[recall / precision]** because [your reasoning: a missed fraud costs money; a false alarm annoys a customer].
- Best model: **[name]** (recall [ ], precision [ ], AUC [ ]).
- Most influential features: [list from your feature-importance chart].

## Scalability
[Your answer on handling 1 million transactions per hour, e.g. lightweight model, batch vs. streaming scoring, retraining schedule.]

## Limitations
[Data caveats, e.g. anonymised features, SMOTE applied only to training data, threshold not tuned, concept drift in real fraud.]

## How to run
```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn jupyter
jupyter notebook [notebook name].ipynb
```

## Demo
- Demo video / LinkedIn post: [paste your link here]
## Dataset

The credit card fraud detection dataset is available on Kaggle:

[Download Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)

After downloading, extract `creditcard.csv` and place it inside this project folder.

**Note:** The dataset is not included in this GitHub repository because its file size exceeds GitHub's standard 100 MB upload limit.