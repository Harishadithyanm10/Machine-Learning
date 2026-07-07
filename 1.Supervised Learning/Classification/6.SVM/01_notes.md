# Support Vector Machine (SVM) — Notes

**What it is:** Finds the hyperplane that maximizes the margin (distance) between the closest points of each class (the "support vectors"). For non-linear boundaries, it uses the **kernel trick** to implicitly map data into higher dimensions.

**Key Hyperparameters (`SVC`):**
| Parameter | Meaning |
|---|---|
| `C` | Regularization strength (inverse). Small C = wider margin, more tolerance for misclassification (softer). Large C = narrower margin, fits training data tighter (can overfit) |
| `kernel` | `'linear'`, `'rbf'` (default, handles non-linear), `'poly'`, `'sigmoid'` |
| `gamma` | For RBF/poly: how far influence of a single point reaches. Small gamma = far reach (smoother), large gamma = close reach (complex, can overfit) |
| `degree` | Degree of polynomial kernel |

**Pros:** Effective in high-dimensional spaces, works well with clear margin of separation, memory efficient (only support vectors matter at prediction).
**Cons:** Slow on large datasets (training scales poorly), sensitive to feature scaling, doesn't directly output probabilities (needs `probability=True`, which adds cost), hard to interpret.

**Critical:** Always scale features — SVM's margin optimization is distance-based, just like KNN.
