# Gradient Boosting — Interview Q&A

**Q1: How is Gradient Boosting different from Random Forest?**
Random Forest builds trees independently in parallel and averages them (bagging, reduces variance). Gradient Boosting builds trees sequentially, each correcting the previous ensemble's errors (reduces bias), and is more sensitive to overfitting/hyperparameters.

**Q2: What does the learning_rate do, and why not just set it very low?**
It scales each tree's contribution to the final prediction — lower rates need more trees to reach the same fit but generalize better. Too low with too few trees underfits; the tradeoff is compute cost.

**Q3: What is the role of the loss function's gradient in this algorithm?**
Each new tree is fit to predict the negative gradient of the loss function with respect to current predictions — essentially "which direction and how much to adjust" each prediction to reduce loss.

**Q4: What is subsample and why would you set it below 1.0?**
It's the fraction of training data randomly used per tree (stochastic gradient boosting) — introduces randomness like bagging, reducing variance/overfitting and speeding up training.

**Q5: Why does Gradient Boosting typically use shallow trees (max_depth 3-5)?**
Each tree is a "weak learner" meant to make a small correction — shallow trees keep the model from fitting too much noise in a single step, letting the boosting process build accuracy gradually and controllably.
