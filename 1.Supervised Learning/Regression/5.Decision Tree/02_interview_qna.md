# Decision Tree Regressor — Interview Q&A

**Q1: How does a regression tree choose its splits, differently from a classification tree?**
It picks splits that minimize variance (MSE) of the target within the resulting child nodes, rather than Gini/Entropy impurity used for class labels.

**Q2: Why can't a decision tree extrapolate beyond the range of training data?**
Each leaf predicts a constant (the average of training samples in that region) — for inputs outside the training range, it still falls into the nearest existing leaf and predicts that same constant, rather than following a trend.

**Q3: What's a key weakness of regression trees vs linear regression on smooth relationships?**
Their predictions are step functions (piecewise constant), so they can approximate a smooth trend only roughly, with visible "steps," unless the tree is very deep.

**Q4: How do you control overfitting in a regression tree?**
Limit `max_depth`, increase `min_samples_leaf`/`min_samples_split`, or use post-pruning (`ccp_alpha`).

**Q5: Why do regression trees form the base of Random Forest and Gradient Boosting?**
They're fast, flexible (capture non-linearity/interactions automatically), and their weaknesses (overfitting, instability) are exactly what ensembling (bagging or boosting) is designed to fix.
