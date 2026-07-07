# Support Vector Regression (SVR) — Notes

**What it is:** The regression counterpart of SVM. Instead of finding a max-margin separating hyperplane, SVR fits a function such that as many points as possible fall within an **epsilon-tube** around the predicted line/curve, only penalizing points that fall outside it.

**Key idea — epsilon-insensitive loss:** Errors smaller than epsilon are ignored (zero loss); only errors beyond epsilon are penalized (linearly, scaled by C). This makes SVR naturally robust to small deviations/noise.

**Key Hyperparameters (`SVR`):**
| Parameter | Meaning |
|---|---|
| `kernel` | `'linear'`, `'rbf'` (default, non-linear), `'poly'` |
| `C` | Regularization — trade-off between flatness of function and tolerating points outside the epsilon-tube |
| `epsilon` | Width of the no-penalty tube around predictions |
| `gamma` | RBF/poly kernel influence radius (like in SVM classification) |

**Pros:** Effective for smaller/medium datasets with complex non-linear relationships (via kernels), robust to small noise thanks to epsilon-tube.
**Cons:** Doesn't scale well to large datasets (like SVM classification), sensitive to feature scaling, requires tuning multiple interacting hyperparameters (C, epsilon, gamma).
