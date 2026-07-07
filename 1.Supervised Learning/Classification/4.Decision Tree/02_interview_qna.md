# Decision Tree — Interview Q&A

**Q1: How does a decision tree decide where to split?**
It evaluates all possible splits across all features and picks the one that most reduces impurity (Gini or Entropy) in the resulting child nodes.

**Q2: What's the difference between Gini Impurity and Entropy?**
Both measure node impurity; Gini is slightly faster to compute and tends to isolate the most frequent class, Entropy is more sensitive to class distribution. In practice they usually produce similar trees.

**Q3: How do you prevent a decision tree from overfitting?**
Limit `max_depth`, increase `min_samples_split`/`min_samples_leaf`, use cost-complexity pruning (`ccp_alpha`), or simply switch to an ensemble method.

**Q4: Why don't decision trees need feature scaling?**
Splits are based on threshold comparisons per feature independently — the scale of one feature doesn't affect how another feature is split.

**Q5: What is pruning and why is it useful?**
Pruning removes branches that provide little predictive power, reducing overfitting and improving generalization. Can be done via pre-pruning (limiting growth, e.g. max_depth) or post-pruning (growing fully then cutting back, e.g. ccp_alpha).
