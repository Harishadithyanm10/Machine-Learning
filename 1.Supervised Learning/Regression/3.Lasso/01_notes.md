# Lasso Regression — Notes

**What it is:** Linear Regression + **L1 regularization** — adds a penalty proportional to the sum of *absolute* coefficient values. Unlike Ridge, this can shrink coefficients to **exactly zero**, effectively performing automatic feature selection.

Loss = SSE + α · Σ|w_i|

**Why coefficients hit exactly zero:** The L1 penalty's geometry (a diamond-shaped constraint region) has corners on the axes, so the optimal solution often lands exactly on an axis (coefficient = 0), unlike L2's smooth circular constraint.

**Key Hyperparameters (`Lasso`):**
| Parameter | Meaning |
|---|---|
| `alpha` | Regularization strength. Higher = more coefficients pushed to zero (sparser model) |
| `max_iter` | Max iterations for the coordinate descent solver |
| `selection` | `'cyclic'` or `'random'` — order of coefficient updates |

**Pros:** Built-in feature selection (sparse, interpretable models), useful with many irrelevant features.
**Cons:** Can arbitrarily drop one feature from a correlated group (unstable choice), requires scaling, can underfit if alpha too high.
