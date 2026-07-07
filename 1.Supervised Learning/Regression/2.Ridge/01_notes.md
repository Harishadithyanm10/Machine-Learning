# Ridge Regression — Notes

**What it is:** Linear Regression + **L2 regularization** — adds a penalty proportional to the sum of squared coefficients to the loss function, shrinking coefficients toward zero (but never exactly zero).

Loss = SSE + α · Σ(w_i)²

**Why it helps:** Reduces variance/overfitting, especially useful when features are highly correlated (multicollinearity) — Ridge distributes weight across correlated features rather than letting one dominate unpredictably.

**Key Hyperparameters (`Ridge`):**
| Parameter | Meaning |
|---|---|
| `alpha` | Regularization strength. 0 = plain Linear Regression. Higher = more shrinkage/simpler model |
| `solver` | Optimization method: `'auto'`, `'svd'`, `'cholesky'`, `'saga'`, etc. |
| `fit_intercept` | Whether to fit the bias term |

**Pros:** Handles multicollinearity well, reduces overfitting, still has a closed-form-like solution (fast).
**Cons:** Doesn't perform feature selection (all coefficients stay non-zero, just smaller), requires tuning alpha, requires feature scaling for the penalty to be fair across features.
