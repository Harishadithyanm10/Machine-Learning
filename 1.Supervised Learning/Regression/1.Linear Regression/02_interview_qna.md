# Linear Regression — Interview Q&A

**Q1: What loss function does Linear Regression minimize, and why squared error?**
Mean/Sum of Squared Error. Squaring penalizes larger errors more, and it's differentiable everywhere (unlike absolute error), giving a clean closed-form solution and stable gradients.

**Q2: What is multicollinearity and why is it a problem?**
When two or more features are highly correlated with each other, making it hard to isolate each one's individual effect — coefficients become unstable and hard to interpret (can even flip signs). Ridge regression or removing/combining features helps.

**Q3: What are the key assumptions of Linear Regression?**
Linearity, homoscedasticity (constant error variance), independence of errors, normally distributed residuals, and low multicollinearity among features.

**Q4: What is R² and what does it mean?**
The proportion of variance in the target explained by the model (1 = perfect fit, 0 = no better than predicting the mean). Can be misleadingly high with many features — use Adjusted R² to penalize for feature count.

**Q5: How would you detect and handle heteroscedasticity (non-constant error variance)?**
Plot residuals vs predicted values — a funnel/cone shape indicates heteroscedasticity. Fixes include transforming the target (e.g., log), using weighted least squares, or switching to a more robust model.
