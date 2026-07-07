# Random Forest (Classification) — Notes

**What it is:** An ensemble of many decision trees, each trained on a random bootstrap sample of the data and a random subset of features per split. Final prediction = majority vote across all trees.

**Why it works (Bagging + Feature Randomness):** Individual trees overfit and are high-variance, but averaging many decorrelated trees cancels out noise and dramatically reduces variance while keeping low bias.

**Key Hyperparameters (`RandomForestClassifier`):**
| Parameter | Meaning |
|---|---|
| `n_estimators` | Number of trees. More = more stable, diminishing returns after a point |
| `max_depth` | Max depth per tree |
| `max_features` | Features considered per split (`'sqrt'` common for classification) |
| `min_samples_leaf` | Min samples per leaf — controls overfitting |
| `bootstrap` | Whether to sample with replacement (True = bagging) |
| `oob_score` | Use out-of-bag samples to estimate accuracy without a separate validation set |

**Pros:** Much less prone to overfitting than a single tree, handles non-linearity and interactions well, gives feature importance, robust to outliers.
**Cons:** Less interpretable than a single tree, slower to predict (must query every tree), can still overfit with too little regularization on noisy data.
