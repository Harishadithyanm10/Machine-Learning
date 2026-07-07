# LightGBM — Notes

**What it is:** "Light Gradient Boosting Machine" — a gradient boosting framework by Microsoft, optimized for speed and memory efficiency on large datasets. Key differences from XGBoost:

- **Leaf-wise tree growth** (vs level-wise in XGBoost/GBM): grows the leaf with the highest loss reduction first, regardless of tree level — can reach lower loss faster, but risks overfitting on small data if unchecked (control via `num_leaves`, `max_depth`).
- **Histogram-based splitting**: buckets continuous features into discrete bins for much faster split-finding, using far less memory.
- **GOSS (Gradient-based One-Side Sampling)**: keeps instances with large gradients (poorly fit so far) and randomly samples from the rest — speeds up training while preserving accuracy.

**Key Hyperparameters (`LGBMRegressor`):**
| Parameter | Meaning |
|---|---|
| `n_estimators` | Boosting rounds |
| `learning_rate` | Shrinkage |
| `num_leaves` | Max leaves per tree — main complexity control (since growth is leaf-wise, not depth-wise) |
| `max_depth` | Optional depth cap to further limit complexity |
| `min_child_samples` | Min data needed in a leaf — controls overfitting on small data |
| `subsample` / `colsample_bytree` | Row / column sampling |

**Pros:** Very fast, memory-efficient, handles large datasets and high-dimensional data well, often matches or beats XGBoost accuracy.
**Cons:** Leaf-wise growth can overfit small datasets more easily than level-wise growth if `num_leaves` isn't controlled; sensitive to hyperparameters on small data.
