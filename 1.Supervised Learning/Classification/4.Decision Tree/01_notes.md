# Decision Tree (Classification) — Notes

**What it is:** A tree of if/else questions on features that splits data into progressively purer subsets, ending in leaf nodes that predict a class.

**How splits are chosen:** At each node, the algorithm picks the feature/threshold that most reduces impurity — measured by **Gini Impurity** (default) or **Entropy/Information Gain**.

Gini = 1 - Σ(p_i)², Entropy = -Σ p_i·log2(p_i)

**Key Hyperparameters (`DecisionTreeClassifier`):**
| Parameter | Meaning |
|---|---|
| `criterion` | `'gini'` or `'entropy'` — impurity measure |
| `max_depth` | Max tree depth — main lever against overfitting |
| `min_samples_split` | Min samples required to split a node |
| `min_samples_leaf` | Min samples required at a leaf node |
| `max_features` | Number of features considered per split |
| `ccp_alpha` | Cost-complexity pruning parameter |

**Pros:** Highly interpretable (can visualize the tree), no scaling needed, handles non-linear relationships and feature interactions naturally.
**Cons:** Prone to overfitting (a fully grown tree memorizes training data), unstable — small data changes can produce a very different tree. Usually improved on by ensembles (Random Forest, Gradient Boosting).
