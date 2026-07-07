# ElasticNet Regression — Notes

**What it is:** Combines **both L1 and L2 penalties** from Lasso and Ridge, controlled by a mixing ratio. Gets sparsity (feature selection) from L1 while handling correlated features more stably thanks to L2.

Loss = SSE + α·[ l1_ratio·Σ|w_i| + (1-l1_ratio)/2·Σ(w_i)² ]

**Key Hyperparameters (`ElasticNet`):**
| Parameter | Meaning |
|---|---|
| `alpha` | Overall regularization strength |
| `l1_ratio` | Mix between L1 and L2. 0 = pure Ridge, 1 = pure Lasso, in-between = blend |
| `max_iter` | Max solver iterations |

**Why use it over pure Lasso/Ridge:** When you have many correlated features AND want some feature selection — pure Lasso would arbitrarily pick one from a correlated group and drop the rest; ElasticNet's L2 component encourages correlated features to shrink together more smoothly, while L1 still zeroes out truly irrelevant ones.

**Pros:** Best of both worlds for correlated + irrelevant features, more stable than pure Lasso.
**Cons:** Two hyperparameters to tune instead of one (`alpha` and `l1_ratio`), still requires scaling.
