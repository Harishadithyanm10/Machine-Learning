# CatBoost — Notes

**What it is:** "Categorical Boosting" — a gradient boosting library built by Yandex, specifically designed to handle **categorical features natively** (no manual one-hot/label encoding needed) using an efficient statistics-based encoding, and using **Ordered Boosting** to reduce prediction shift/target leakage.

**Why it's different:**
- Native categorical handling: pass raw category columns directly via `cat_features` parameter.
- Ordered Target Statistics: encodes categories using only "past" data in a random permutation, avoiding target leakage that plain target encoding suffers from.
- Symmetric ("oblivious") trees: same split condition across an entire tree level, which is faster at inference and acts as regularization.

**Key Hyperparameters (`CatBoostClassifier`):**
| Parameter | Meaning |
|---|---|
| `iterations` | Number of boosting rounds |
| `learning_rate` | Shrinkage per round |
| `depth` | Tree depth (usually 4-10, symmetric trees) |
| `l2_leaf_reg` | L2 regularization on leaf values |
| `cat_features` | List of column indices/names to treat as categorical |
| `early_stopping_rounds` | Stop when validation metric stops improving |

**Pros:** Excellent with categorical-heavy data out of the box, strong default performance (less tuning needed), robust to overfitting via ordered boosting.
**Cons:** Can be slower to train than XGBoost/LightGBM on purely numeric data, larger library/less ubiquitous tooling.
