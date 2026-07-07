# XGBoost (Classification) — Notes

**What it is:** "Extreme Gradient Boosting" — an optimized, regularized implementation of gradient boosting. Adds L1/L2 regularization on leaf weights, second-order gradient (Newton's method) approximation, built-in handling of missing values, and highly parallelized tree construction.

**Why it improved on plain Gradient Boosting:** Faster (parallel/histogram-based split finding), regularized (less overfitting), handles missing data natively, built-in cross-validation and early stopping.

**Key Hyperparameters (`XGBClassifier`):**
| Parameter | Meaning |
|---|---|
| `n_estimators` | Number of boosting rounds |
| `learning_rate` (eta) | Shrinkage per round |
| `max_depth` | Tree depth |
| `subsample` | Row sampling ratio per tree |
| `colsample_bytree` | Column (feature) sampling ratio per tree |
| `reg_alpha` / `reg_lambda` | L1 / L2 regularization on leaf weights |
| `min_child_weight` | Min sum of instance weight needed in a child — controls overfitting |
| `early_stopping_rounds` | Stop training if validation score doesn't improve |

**Pros:** State-of-the-art accuracy on tabular data, built-in regularization reduces overfitting vs plain GBM, fast, handles missing values automatically.
**Cons:** Many hyperparameters to tune, can still overfit without care, less interpretable than a single tree.
