# XGBoost Regressor — Interview Q&A

**Q1: What regularization terms does XGBoost add to the objective function?**
L1 (`reg_alpha`) and L2 (`reg_lambda`) penalties on the leaf weight values, plus an implicit penalty on the number of leaves — all combined to control tree complexity directly in the loss function being optimized.

**Q2: How does XGBoost use second-order gradient information, and why does it help?**
It uses both the gradient (first derivative) and Hessian (second derivative) of the loss to determine each tree's optimal leaf values — this gives more accurate, Newton-method-style updates than using gradient alone, often converging faster/better.

**Q3: What's the practical benefit of colsample_bytree and subsample together in regression?**
Both introduce randomness (feature and row subsampling per tree), reducing correlation between trees and helping prevent overfitting, similar in spirit to Random Forest's randomness but within a boosting framework.

**Q4: How would you use early stopping with XGBRegressor?**
Pass an `eval_set` (validation data) and `early_stopping_rounds` — training halts once the validation metric stops improving for that many rounds, avoiding wasted rounds and overfitting.

**Q5: What's a real advantage of XGBoost's native missing value handling in regression tasks?**
It learns the optimal default split direction for missing values directly from training data loss reduction, avoiding potentially biased manual imputation strategies (like mean/median filling) that can distort the true relationship.
