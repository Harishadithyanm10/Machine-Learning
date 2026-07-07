# SVM — Interview Q&A

**Q1: What are support vectors?**
The data points closest to the decision boundary — they alone define the margin and hyperplane. All other points could be removed without changing the decision boundary.

**Q2: What is the kernel trick?**
A method to compute the effect of mapping data into a higher-dimensional space (where it may be linearly separable) without ever explicitly transforming the data — done via a kernel function measuring similarity in the original space.

**Q3: What happens with a very large C?**
The model tries hard to classify every training point correctly (narrow/hard margin), which can lead to overfitting and sensitivity to outliers.

**Q4: What does gamma control in the RBF kernel, and what happens if it's too high?**
It controls how far a single training example's influence reaches. Too high gamma = only nearby points matter = the model fits training data very tightly = overfitting (like a very flexible/wiggly boundary).

**Q5: Why is SVM slow on large datasets?**
Standard SVM training complexity is roughly O(n²) to O(n³) with the number of samples, since it involves solving a quadratic optimization problem over all pairs of points.
