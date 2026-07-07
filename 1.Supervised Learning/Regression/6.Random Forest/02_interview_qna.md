# Random Forest Regressor — Interview Q&A

**Q1: How does Random Forest regression combine individual tree predictions?**
By averaging the predictions of all trees (as opposed to majority voting used in classification).

**Q2: Why can Random Forest not extrapolate beyond the training data's target range?**
Because every tree's leaf prediction is an average of training targets seen in that region — averaging many such bounded predictions still can't produce values outside the observed range.

**Q3: What's the effect of increasing max_features in a regression forest?**
More features considered per split makes individual trees more similar/correlated to each other (less randomness), which can increase accuracy on some tasks but reduces the variance-reduction benefit of the ensemble.

**Q4: Why might Random Forest regression sometimes underperform Gradient Boosting?**
Random Forest reduces variance well but doesn't actively correct systematic bias/errors the way sequential boosting does — on tasks needing very fine-grained accuracy, boosting often edges it out (at the cost of more tuning/risk of overfitting).

**Q5: How would you estimate Random Forest's generalization error without a separate validation set?**
Use the OOB (out-of-bag) score — each tree's unseen ~37% of bootstrap data acts as a free internal validation set.
