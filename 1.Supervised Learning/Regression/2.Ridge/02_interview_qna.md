# Ridge Regression — Interview Q&A

**Q1: How does Ridge Regression differ from plain Linear Regression?**
It adds an L2 penalty (sum of squared coefficients) to the loss function, shrinking coefficients toward zero to reduce variance/overfitting, at the cost of a small increase in bias.

**Q2: Why is feature scaling important before Ridge?**
The penalty term treats all coefficients equally in magnitude — if features are on different scales, the penalty unfairly shrinks large-scale features' coefficients more/less than intended.

**Q3: Does Ridge perform feature selection? Why or why not?**
No — L2 penalty shrinks coefficients smoothly toward zero but essentially never makes them exactly zero, so all features remain in the model (just with reduced weight).

**Q4: How do you choose the alpha hyperparameter?**
Use cross-validation (e.g., `RidgeCV`) across a range of alpha values and pick the one with the best validation performance (lowest error).

**Q5: When would you prefer Ridge over Lasso?**
When you believe most/all features are relevant and want to keep them all (just shrunk), or when features are highly correlated — Ridge handles correlated groups of features more gracefully than Lasso, which tends to arbitrarily pick one from a correlated group.
