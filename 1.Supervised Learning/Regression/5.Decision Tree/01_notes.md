# Decision Tree (Regression) — Notes

**What it is:** Same tree-splitting idea as classification, but each leaf predicts the **average target value** of training samples that land there, and splits are chosen to minimize **variance/MSE** within child nodes instead of Gini/Entropy.

**Key Hyperparameters (`DecisionTreeRegressor`):**
| Parameter | Meaning |
|---|---|
| `criterion` | `'squared_error'` (default), `'absolute_error'`, `'friedman_mse'` |
| `max_depth` | Max tree depth — main overfitting control |
| `min_samples_split` / `min_samples_leaf` | Min samples to split / at a leaf |
| `max_features` | Features considered per split |

**Pros:** Captures non-linear relationships and interactions, no scaling needed, interpretable.
**Cons:** Predictions are step-functions (constant within each leaf region) — can't extrapolate beyond training range, prone to overfitting if unrestricted, unstable with small data changes.
