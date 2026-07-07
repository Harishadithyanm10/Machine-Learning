# K-Nearest Neighbors (KNN) — Notes

**What it is:** A lazy, instance-based algorithm. To classify a new point, it looks at the `k` closest points in the training data (by distance, usually Euclidean) and takes a majority vote of their labels.

**Intuition:** "You are the average of your neighbors." No explicit training phase — it just memorizes the data and does the work at prediction time.

**Key Hyperparameters (`KNeighborsClassifier`):**
| Parameter | Meaning |
|---|---|
| `n_neighbors` (k) | Number of neighbors to consider. Small k = low bias/high variance (noisy). Large k = high bias/low variance (smoother, may underfit) |
| `weights` | `'uniform'` (equal vote) or `'distance'` (closer neighbors count more) |
| `metric` | Distance metric: `'minkowski'` (default, p=2 = Euclidean), `'manhattan'`, `'chebyshev'` |
| `p` | Power parameter for Minkowski distance |
| `algorithm` | `'auto'`, `'ball_tree'`, `'kd_tree'`, `'brute'` — affects speed, not results |

**Pros:** Simple, no training time, naturally handles multi-class, non-linear decision boundaries.
**Cons:** Slow at prediction time (must compare to all points), sensitive to feature scale, suffers in high dimensions (curse of dimensionality), sensitive to irrelevant features and outliers.

**Critical:** Always scale features before KNN — distance-based, so unscaled features dominate.
