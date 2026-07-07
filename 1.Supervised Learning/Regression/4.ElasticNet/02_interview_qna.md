# ElasticNet — Interview Q&A

**Q1: Why would you use ElasticNet instead of Ridge or Lasso alone?**
When your data has groups of correlated features and you also want feature selection — Lasso alone would arbitrarily pick one feature per correlated group (unstable), while ElasticNet's L2 component lets correlated features shrink together more sensibly while still zeroing out truly irrelevant ones.

**Q2: What does l1_ratio control?**
The blend between L1 and L2 penalty. l1_ratio=1 is pure Lasso, l1_ratio=0 is pure Ridge, and values in between blend both effects.

**Q3: How do you tune ElasticNet's hyperparameters efficiently?**
Use `ElasticNetCV`, which searches over a grid of `alpha` and `l1_ratio` values via cross-validation simultaneously.

**Q4: In what scenario would ElasticNet clearly outperform plain Lasso?**
When there are groups of highly correlated predictive features — Lasso tends to pick just one from each group somewhat arbitrarily, while ElasticNet's L2 term helps distribute weight more stably across the correlated group.

**Q5: Does ElasticNet still require feature scaling? Why?**
Yes — both its L1 and L2 penalty components are scale-sensitive, just like Ridge and Lasso individually.
