# Random Forest — Interview Q&A

**Q1: How does Random Forest reduce overfitting compared to a single decision tree?**
By averaging predictions across many trees trained on different bootstrap samples and random feature subsets, individual trees' errors (variance) cancel out, while the ensemble's bias stays similar to a single deep tree.

**Q2: What is bagging?**
Bootstrap Aggregating — training multiple models on random samples (with replacement) of the training data, then combining their predictions (vote/average) to reduce variance.

**Q3: What is the OOB (out-of-bag) score?**
Since each tree only sees ~63% of data (bootstrap sampling), the remaining ~37% ("out-of-bag") can be used to validate that tree — giving a free, built-in validation estimate without a separate holdout set.

**Q4: Why does Random Forest use a random subset of features at each split, not just bootstrap sampling?**
Without it, if one feature is very strong, most trees would split on it early, making trees highly correlated — reducing the variance-reduction benefit of averaging. Random feature selection decorrelates the trees.

**Q5: How do you get feature importance from a Random Forest, and what's a caveat?**
`model.feature_importances_` (based on impurity decrease). Caveat: it's biased toward high-cardinality/continuous features and can be misleading with correlated features — permutation importance is often more reliable.
