# SVR — Interview Q&A

**Q1: What is the epsilon-insensitive loss function in SVR?**
A loss function that assigns zero penalty to prediction errors smaller than epsilon, and only penalizes (linearly) errors that exceed epsilon — this creates a "tube" around the fitted function where small deviations are tolerated.

**Q2: How does the epsilon parameter affect model complexity?**
A larger epsilon creates a wider tolerance tube, allowing a simpler/flatter function and fewer support vectors (less complex model); a smaller epsilon forces tighter fitting, potentially more support vectors and complexity.

**Q3: What's the role of C in SVR, and how does it interact with epsilon?**
C controls how much to penalize points outside the epsilon-tube — high C forces the model to fit those points tightly (risking overfitting), low C allows more tolerance. The two parameters need to be tuned together, since a wide epsilon with low C both push toward a simpler model.

**Q4: Why does SVR need feature scaling just like SVM classification?**
Both rely on distance/margin calculations in the kernel space — unscaled features would disproportionately affect the epsilon-tube and kernel similarity calculations.

**Q5: In what situations would you avoid using SVR?**
On very large datasets (training scales poorly, roughly O(n²) to O(n³)), or when you need fast, easily interpretable models — tree ensembles (Random Forest, XGBoost) often scale better and need less careful kernel/hyperparameter tuning.
