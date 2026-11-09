# Data Analytics · Level 2 · Task 2 — Wine Quality Prediction

**Oasis Infobyte Internship Program (OIBSIP)** · Track: Data Analytics

## Objective
Train and compare three classifiers (Random Forest, SGD, SVC) that predict wine quality from physicochemical properties.

## Dataset
UCI **Wine Quality** (white *Vinho Verde*), `winequality-white.csv`: 4,898 samples, 11 features, quality score 3–9. Source: Cortez et al. (2009), UCI Machine Learning Repository.

## Files
| File | Description |
|---|---|
| `Task2_Wine_Quality_Prediction.ipynb` | Full analysis with written observations |
| `winequality-white.csv` | Dataset (semicolon-separated) |
| `screenshots/` | Exported charts |

## Tech Stack
Python · pandas · numpy · scikit-learn (RandomForest, SGD, SVC) · seaborn · matplotlib · Jupyter Notebook

## Approach
1. Inspect structure, nulls and class distribution (7 quality scores, very imbalanced: 5 wines at quality 9)
2. EDA: feature histograms and correlation heatmap
3. **Class imbalance discussion**, then bin quality into 3 classes (low 3–5, medium 6, high 7–9)
4. **Duplicate handling:** 937 duplicate rows removed (data leakage, see below)
5. Stratified 80/20 split; `StandardScaler` inside a pipeline for SGD and SVC; `class_weight="balanced"`
6. Evaluate each model: accuracy, classification report, confusion matrix
7. Random Forest feature importance, model comparison table, 5-fold cross-validation

## Results (test set, 793 wines)
| Model | Accuracy | Macro F1 | 5-fold CV Macro F1 |
|---|---|---|---|
| **Random Forest** | **0.591** | **0.591** | **0.600 ± 0.015** |
| SVC | 0.564 | 0.563 | 0.567 ± 0.024 |
| SGD | 0.507 | 0.500 | 0.504 ± 0.019 |

## Key findings
- **Duplicates caused data leakage:** keeping the 937 duplicate rows inflated Random Forest accuracy to 71.6% (vs 59.1% after removal).
- **Alcohol** is the strongest predictor (correlation +0.44; most important Random Forest feature), followed by density and volatile acidity.
- The **medium** class is the hardest to predict for every model; the linear SGD model almost fails on it.
- **Random Forest** is the most suitable model: best scores, most balanced across classes, and interpretable.
- Quality scores come from subjective tasting, so ~59% accuracy is best used as a screening aid, not a replacement for tasters.

## Limitations
No hyperparameter tuning (SVC could improve), a single dataset (white wine only), and results may vary slightly across library versions.

## How to run
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook Task2_Wine_Quality_Prediction.ipynb
```

## Demo
- Demo video / LinkedIn post: [paste your link here]
