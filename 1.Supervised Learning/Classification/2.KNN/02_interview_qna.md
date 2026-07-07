# KNN — Interview Q&A

**Q1: Why does KNN need feature scaling but a decision tree doesn't?**
KNN relies on distance calculations — a feature with a larger numeric range will dominate the distance metric. Trees split on thresholds per feature independently, so scale doesn't matter.

**Q2: How do you choose the right value of k?**
Use cross-validation to test a range of k values and pick the one with best validation performance. Rule of thumb: try odd k (avoids ties in binary classification), sqrt(n) is a common starting point.

**Q3: What is the curse of dimensionality and how does it affect KNN?**
As dimensions increase, distances between points become less meaningful (everything becomes "far"), making neighbors less informative. Dimensionality reduction (PCA) or feature selection helps.

**Q4: What's the time complexity of KNN prediction?**
O(n·d) per query for brute-force (n = training samples, d = dimensions), since it computes distance to every point. KD-trees/Ball-trees speed this up in lower dimensions.

**Q5: Difference between KNN and K-Means?**
KNN is supervised (classification/regression using labeled neighbors); K-Means is unsupervised clustering (finds groups without labels). Same "K" and distance idea, totally different purpose.
