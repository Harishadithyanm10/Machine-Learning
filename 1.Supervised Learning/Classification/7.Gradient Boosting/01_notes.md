# Gradient Boosting (Classification) — Notes

**What it is:** An ensemble built **sequentially** — each new tree is trained to correct the errors (residuals of the loss gradient) of the combined ensemble so far, unlike Random Forest's parallel independent trees.

**Core idea:** Start with a simple prediction, compute the loss gradient (how wrong you are), fit a small tree to predict that gradient, add it (scaled by learning rate) to the ensemble, repeat.

**Key Hyperparameters (`GradientBoostingClassifier`):**
| Parameter | Meaning |
|---|---|
| `n_estimators` | Number of boosting stages (trees) |
| `learning_rate` | Shrinks each tree's contribution — lower = needs more trees but generalizes better |
| `max_depth` | Depth of each individual tree (usually shallow, 3-5) |
| `subsample` | Fraction of samples used per tree (< 1.0 = stochastic gradient boosting, reduces overfitting) |
| `min_samples_leaf` | Min samples per leaf |

**Pros:** Often top-tier accuracy, handles mixed feature types and non-linearity very well.
**Cons:** Sequential training = slower than Random Forest (can't parallelize across trees), more hyperparameter-sensitive, can overfit if `learning_rate` too high or too many estimators without early stopping.

**Bias-Variance:** Boosting mainly reduces bias (weak learners combine into a strong one); bagging (Random Forest) mainly reduces variance.
