---
title: "Multiple Linear Regression"
---

Statistical technique that uses two or more independent variables to predict the outcome of a dependent variable
- determine the relative contribution of each independent variable in total variance

Equation of Multiple Linear Regression:
$y = b_0 + b_1X_1 + b_2X_2 + + b_3X_3 + ... + b_nX_n$
- $y$ is the dependent variable, $b_0$ is the y-intercept (constant), and $X_n$ is the independent variable (with a slope coefficient)

**Dummy Variables**
For categorical variables, how can we represent them in a multiple linear regression equation? We can use dummy variables - **variable that takes values of 0 and 1, where the values indicate the presence or absence of something**. For each level of categorical variable, we assign a dummy variable and use that in our equation.

*Dummy Variable Trap*
- Attributes that are highly correlated and one variable predicts the others.
- Occurs with one-hot encoding of categorical data where one dummy variable predicts the other
- Results in multicollinearity, affecting regression models
- Solution: remove one dummy variable!

