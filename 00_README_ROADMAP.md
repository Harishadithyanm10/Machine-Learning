# ML Self-Learning Roadmap

## How this folder works
Every algorithm folder contains:
1. `01_notes.md` — concept, intuition, key hyperparameters, pros/cons
2. `02_interview_qna.md` — common interview questions with answers
3. `03_project1_....ipynb` — a fully worked, executed example (different synthetic dataset per model)
   - The **last markdown cell of every Project 1 notebook** also contains your **Project 2 instructions**: a different real dataset (from sklearn/seaborn, no internet download needed beyond what's built into those libraries) for you to practice the same algorithm alone.

## Roadmap

### 1. Supervised Learning
**Classification**
1. Logistic Regression
2. KNN
3. Naive Bayes
4. Decision Tree
5. Random Forest
6. SVM
7. Gradient Boosting
8. XGBoost
9. CatBoost

**Regression**
1. Linear Regression
2. Ridge
3. Lasso
4. ElasticNet
5. Decision Tree
6. Random Forest
7. Gradient Boosting
8. XGBoost
9. LightGBM
10. SVR

### 2. Unsupervised Learning (next phase)
Clustering (K-Means, Hierarchical, DBSCAN), Dimensionality Reduction (PCA, t-SNE, UMAP), Association Rules (Apriori)

### 3. Reinforcement Learning (final phase)
Q-Learning, SARSA, Deep Q-Networks (DQN), Policy Gradient methods

## Suggested workflow per model
1. Read `01_notes.md` — understand the concept before touching code.
2. Read `02_interview_qna.md` — solidify understanding by seeing how it's tested.
3. Open `03_project1_*.ipynb` — run it, read every cell's comments, make sure you understand *why* each step exists, not just what it does.
4. Do Project 2 **alone** using the dataset given in the last cell of the Project 1 notebook — don't look at Project 1's code while doing it.
5. Only move to the next algorithm once Project 2 is done.

When you finish all of Supervised Learning, message me and we'll build out Unsupervised Learning next, in the same structure.
