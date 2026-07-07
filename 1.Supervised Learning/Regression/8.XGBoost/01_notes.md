# XGBoost (Regression) — Notes

**What it is:** Same core idea as Gradient Boosting Regressor, but with XGBoost's efficiency/regularization upgrades: L1/L2 penalties on leaf weights, second-order gradient approximation, native missing value handling, and highly optimized/parallelized training.

**Key Hyperparameters (`XGBRegressor`):**
| Parameter | Meaning |
|---|---|
| `n_estimators` | Boosting rounds |
| `learning_rate` | Shrinkage |
| `max_depth` | Tree depth |
| `subsample` / `colsample_bytree` | Row / column sampling ratios |
| `reg_alpha` / `reg_lambda` | L1 / L2 regularization |
| `objective` | `'reg:squarederror'` (default), `'reg:absoluteerror'`, etc. |

**Pros:** Typically faster and more accurate than plain sklearn GradientBoosting, strong regularization reduces overfitting, handles missing data natively.
**Cons:** More hyperparameters, needs careful tuning to avoid overfitting on smaller datasets.
