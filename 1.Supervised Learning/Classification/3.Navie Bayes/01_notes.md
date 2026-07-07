# Naive Bayes — Notes

**What it is:** A probabilistic classifier based on Bayes' Theorem, with the "naive" assumption that all features are conditionally independent given the class.

P(class | features) ∝ P(class) × Π P(feature_i | class)

**Variants:**
- `GaussianNB`: continuous features, assumes normal distribution
- `MultinomialNB`: count data (e.g., word counts in text)
- `BernoulliNB`: binary/boolean features

**Key Hyperparameters:**
| Parameter | Meaning |
|---|---|
| `var_smoothing` (Gaussian) | Adds small variance to avoid zero-probability issues |
| `alpha` (Multinomial/Bernoulli) | Laplace/Lidstone smoothing — avoids zero probability for unseen feature/class combos |
| `fit_prior` | Whether to learn class priors from data or assume uniform |

**Pros:** Extremely fast to train and predict, works well with high-dimensional data (e.g., text), needs little training data, naturally handles multi-class.
**Cons:** Independence assumption is rarely true in practice (still works surprisingly well), poor probability calibration, struggles when features are highly correlated.

**Classic use case:** Spam detection, sentiment analysis, document classification.
