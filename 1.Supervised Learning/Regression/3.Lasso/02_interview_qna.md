# Lasso Regression — Interview Q&A

**Q1: Why can Lasso (L1) zero out coefficients while Ridge (L2) cannot?**
Geometrically, L1's constraint region is a diamond with sharp corners on the axes — optimal solutions often land exactly on a corner (some coefficients = 0). L2's constraint region is a smooth circle/ellipse with no corners, so solutions rarely land exactly at zero.

**Q2: When would you choose Lasso over Ridge?**
When you suspect many features are irrelevant and want automatic feature selection, or when you want a sparser, more interpretable model with fewer active features.

**Q3: What's a downside of Lasso with correlated features?**
It tends to arbitrarily pick one feature from a group of correlated features and zero out the rest, even if they're all similarly informative — the specific choice can be unstable across different samples of data.

**Q4: How do you pick the alpha value for Lasso?**
Cross-validation (`LassoCV`) — plot validation error across a range of alphas and pick the value that minimizes it, or use the "1 standard error rule" for a slightly simpler model.

**Q5: What is Elastic Net and why might it be preferred over pure Lasso?**
It combines L1 and L2 penalties — this fixes Lasso's instability with correlated features (L2 part) while still allowing sparsity/feature selection (L1 part).
