# Naive Bayes — Interview Q&A

**Q1: Why is it called "naive"?**
Because it assumes all features are independent given the class label — an assumption almost never true in real data, yet the model still performs well in practice.

**Q2: Why does Naive Bayes work well despite the unrealistic independence assumption?**
It only needs to rank probabilities correctly (which class is most likely), not estimate them precisely. Even with correlated features, the relative ordering of class probabilities often stays correct.

**Q3: What is Laplace smoothing and why is it needed?**
It adds a small constant (`alpha`) to feature counts to prevent zero probability when a feature value never appears with a class in training data — otherwise that zero would zero out the entire product.

**Q4: When would you use MultinomialNB vs GaussianNB?**
MultinomialNB for discrete/count data (word frequencies in text). GaussianNB for continuous numeric features assumed roughly normal.

**Q5: Is Naive Bayes generative or discriminative?**
Generative — it models P(features|class) and P(class) to derive P(class|features) via Bayes' theorem, unlike discriminative models (like logistic regression) that directly model P(class|features).
