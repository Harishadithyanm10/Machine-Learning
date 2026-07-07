# Gradient Boosting (Regression) — Notes

**What it is:** Sequentially builds trees where each new tree predicts the **residual errors** (for squared-error loss, literally `y - current_prediction`) of the ensemble so far, and adds it in (scaled by `learning_rate`).

**Key Hyperparameters (`GradientBoostingRegressor`):**
| Parameter | Meaning |
|---|---|
| `n_estimators` | Number of boosting stages |
| `learning_rate` | Shrinks each tree's contribution |
| `max_depth` | Depth per tree (usually shallow, 3-5) |
| `subsample` | Row sampling ratio per tree (stochastic GB) |
| `loss` | `'squared_error'`, `'absolute_error'`, `'huber'` (robust to outliers), `'quantile'` |

**Pros:** Often best-in-class accuracy on tabular regression, `huber`/`quantile` loss options add robustness/flexibility that plain squared-error models lack.
**Cons:** Sequential (slower to train than RF), sensitive to hyperparameters/overfitting, needs careful tuning of learning_rate + n_estimators together.
