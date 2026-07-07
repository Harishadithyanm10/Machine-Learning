# Linear Regression — Notes

**What it is:** Models the relationship between features and a continuous target as a straight line (or hyperplane): y = w0 + w1x1 + ... + wnxn. Learns weights that minimize the **Sum of Squared Errors (SSE)**.

**How it learns:** Closed-form via Normal Equation (w = (XᵀX)⁻¹Xᵀy) for small data, or gradient descent for large data.

**Key Hyperparameters (`LinearRegression`):**
| Parameter | Meaning |
|---|---|
| `fit_intercept` | Whether to fit the bias term w0 |
| `positive` | Force all coefficients to be non-negative |
| *(no regularization param — plain OLS)* | Use Ridge/Lasso/ElasticNet if you need regularization |

**Assumptions:** Linear relationship between X and y, residuals are normally distributed with constant variance (homoscedasticity), features are not highly collinear (multicollinearity inflates coefficient variance), no autocorrelation in residuals.

**Pros:** Extremely interpretable, fast, a strong baseline.
**Cons:** Can't capture non-linear relationships, sensitive to outliers, unstable coefficients with multicollinearity, no built-in regularization (can overfit with many features).
