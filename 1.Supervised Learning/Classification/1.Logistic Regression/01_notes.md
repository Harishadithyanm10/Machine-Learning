# Logistic Regression — Notes

**What it is:** A classification algorithm (not regression) that predicts the probability of a binary/multi-class outcome using the sigmoid function:

P(y=1|x) = 1 / (1 + e^-(w0 + w1x1 + ... + wnxn))

**How it learns:** Minimizes log loss (binary cross-entropy) via gradient descent — convex, unlike squared error would be here.

**Key Hyperparameters (`LogisticRegression`):**
| Parameter | Meaning |
|---|---|
| `penalty` | `'l1'`, `'l2'` (default), `'elasticnet'`, `'none'` |
| `C` | Inverse regularization strength — smaller C = stronger regularization |
| `solver` | `'lbfgs'`, `'liblinear'`, `'saga'`, `'newton-cg'` |
| `max_iter` | Max iterations to converge |
| `class_weight` | `'balanced'` helps with imbalanced classes |
| `multi_class` | `'ovr'` or `'multinomial'` |

**Assumptions:** Roughly linear decision boundary, low multicollinearity, works best with linearly separable classes.

**Pros:** Fast, interpretable (coefficients = log-odds), outputs calibrated-ish probabilities, strong baseline.
**Cons:** Struggles with non-linear boundaries, sensitive to outliers, needs scaling for regularization to behave correctly.
