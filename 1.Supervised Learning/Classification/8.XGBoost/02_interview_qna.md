# XGBoost — Interview Q&A

**Q1: What does XGBoost add on top of standard Gradient Boosting?**
L1/L2 regularization on leaf weights, second-order gradient information (uses both gradient and Hessian for more accurate updates), parallelized/histogram-based split finding for speed, and native missing-value handling.

**Q2: How does XGBoost handle missing values?**
It learns a default direction (left or right) for missing values at each split during training, based on which direction minimizes loss — no manual imputation required.

**Q3: What's the purpose of colsample_bytree?**
Randomly samples a subset of features for each tree, similar to Random Forest's feature randomness — reduces correlation between trees and helps prevent overfitting.

**Q4: What is early stopping and why use it?**
Training stops once validation performance stops improving for a set number of rounds (`early_stopping_rounds`), preventing overfitting and saving compute instead of blindly training all `n_estimators`.

**Q5: How does XGBoost's regularization differ from plain Gradient Boosting?**
XGBoost explicitly penalizes leaf weight magnitude and tree complexity (number of leaves) in its objective function, whereas plain sklearn GradientBoosting relies mainly on tree depth/learning rate/subsampling to control complexity.
