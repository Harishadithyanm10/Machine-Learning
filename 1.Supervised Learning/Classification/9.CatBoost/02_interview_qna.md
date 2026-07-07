# CatBoost — Interview Q&A

**Q1: What is CatBoost's biggest advantage over XGBoost/LightGBM?**
Native, efficient handling of categorical features without manual encoding — it uses ordered target statistics internally, avoiding the overfitting risk of naive target encoding.

**Q2: What is "Ordered Boosting" and what problem does it solve?**
It trains using a random permutation of the data and only uses "past" examples (earlier in the permutation) to compute statistics/residuals for each example — preventing the target leakage that occurs when all data is used to encode categories.

**Q3: What are symmetric (oblivious) trees?**
Trees where the same feature/threshold split is used across all nodes at a given depth level. This makes predictions faster (can be vectorized) and acts as a regularizer, reducing overfitting risk.

**Q4: How do you tell CatBoost which columns are categorical?**
Pass their column names/indices via the `cat_features` parameter — CatBoost then handles their encoding internally rather than requiring one-hot or label encoding beforehand.

**Q5: When would you prefer CatBoost over XGBoost?**
When your dataset has many categorical features (especially high-cardinality ones) and you want strong performance with minimal preprocessing/tuning effort.
