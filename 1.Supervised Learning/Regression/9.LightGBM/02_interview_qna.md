# LightGBM — Interview Q&A

**Q1: What is the key structural difference between LightGBM and XGBoost's tree growth?**
LightGBM grows trees leaf-wise (always splitting the leaf with the highest loss reduction next), while XGBoost traditionally grows level-wise (splitting every leaf at the current depth before going deeper). Leaf-wise can reach lower loss with fewer splits but risks overfitting on small data.

**Q2: Why is LightGBM faster than traditional Gradient Boosting on large datasets?**
It uses histogram-based binning of continuous features (reducing split-finding to comparing bins rather than every unique value) and GOSS sampling (focusing on poorly-fit instances), both of which cut computation significantly.

**Q3: What is GOSS and what problem does it solve?**
Gradient-based One-Side Sampling — keeps all instances with large gradients (under-fit so far, most informative) and randomly samples a subset of well-fit instances, speeding up training while still representing the overall data distribution well.

**Q4: Why is num_leaves such an important parameter in LightGBM?**
Since trees grow leaf-wise (not depth-limited by default), num_leaves directly controls model complexity/overfitting risk — a high num_leaves with leaf-wise growth can create deep, overfit trees much faster than level-wise growth would.

**Q5: When would you prefer LightGBM over XGBoost?**
On larger datasets or higher-dimensional data where training speed and memory matter — LightGBM's histogram binning and GOSS give it an edge, though on small datasets XGBoost's level-wise growth may generalize a bit more safely by default.
