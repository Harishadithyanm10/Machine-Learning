# Logistic Regression — Interview Q&A

**Q1: Why is it called "regression" if it's used for classification?**
Because internally it fits a linear regression-like equation, then passes it through the sigmoid to convert the output into a probability.

**Q2: Why not use linear regression for classification?**
Linear regression outputs unbounded values, doesn't model probabilities well, and squared error loss isn't ideal for classification.

**Q3: What loss function does it use, and why?**
Log loss (cross-entropy) — convex for logistic regression, heavily penalizes confident wrong predictions, and derives from maximum likelihood estimation.

**Q4: What does a feature's coefficient mean?**
The change in log-odds of the outcome per unit increase in that feature, holding others constant. Exponentiating it gives the odds ratio.

**Q5: How do you handle multi-class classification with logistic regression?**
One-vs-Rest (train one binary classifier per class) or Softmax/Multinomial logistic regression.

**Q6: What's the effect of the regularization parameter C?**
Small C = strong regularization, simpler model. Large C = weak regularization, can overfit.

**Q7: Does logistic regression require feature scaling?**
Not strictly for prediction, but strongly recommended for regularization and solver convergence.

**Q8: How do you handle imbalanced datasets?**
`class_weight='balanced'`, resampling (SMOTE/undersampling), or adjusting the decision threshold.

**Q9: Difference between L1 and L2 regularization here?**
L1 can shrink coefficients to exactly 0 (feature selection). L2 shrinks smoothly, rarely to zero.
