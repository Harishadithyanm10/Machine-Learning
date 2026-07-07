# Random Forest (Regression) — Notes

**What it is:** Ensemble of regression trees, each trained on a bootstrap sample with random feature subsets per split. Final prediction = **average** of all trees' predictions (instead of majority vote for classification).

**Key Hyperparameters (`RandomForestRegressor`):**
| Parameter | Meaning |
|---|---|
| `n_estimators` | Number of trees |
| `max_depth` | Depth per tree |
| `max_features` | Features per split (`1.0`/`'sqrt'` common for regression — often higher than classification default) |
| `min_samples_leaf` | Min samples per leaf |
| `oob_score` | Free validation estimate from out-of-bag samples |

**Pros:** Smooths out the step-function weakness of a single tree (averaging many trees approximates smoother functions), robust to outliers and overfitting compared to a single tree.
**Cons:** Still can't extrapolate beyond training data range (bounded by leaf averages), less interpretable, slower prediction than a single tree.
