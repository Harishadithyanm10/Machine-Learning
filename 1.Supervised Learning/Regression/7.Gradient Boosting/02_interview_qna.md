# Gradient Boosting Regressor — Interview Q&A

**Q1: What exactly does each new tree in Gradient Boosting regression predict?**
The negative gradient of the loss function w.r.t. current predictions — for squared error loss, this is simply the current residuals (actual - predicted).

**Q2: Why would you use Huber loss instead of squared error?**
Huber loss behaves like squared error for small residuals but like absolute error for large ones, making it more robust to outliers that would otherwise dominate a squared-error-based model.

**Q3: How do learning_rate and n_estimators interact?**
Lower learning_rate needs more n_estimators to fit the data equally well, but generally generalizes better; this tradeoff is often tuned together rather than independently.

**Q4: What is quantile regression via Gradient Boosting used for?**
Predicting a specific percentile of the target distribution (e.g., 90th percentile) instead of the mean — useful for building prediction intervals or risk-averse estimates.

**Q5: Why is Gradient Boosting regression prone to overfitting if left unchecked?**
Since each tree actively fits the previous ensemble's remaining errors, given enough rounds it can start fitting noise in the training residuals rather than genuine signal — hence the need for shallow trees, subsampling, and a validation-based stopping point.
