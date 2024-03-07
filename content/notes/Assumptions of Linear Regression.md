---
title: Assumptions of Linear Regression
tags:
  - Areas
---
Anscombe's Quartet - A group of four data sets with nearly identical descriptive statistics, yet different distributions and graphs. These are prime examples of why it's important to be selective on when to use linear regression!

![](https://matplotlib.org/stable/_images/sphx_glr_anscombe_001.png)

  
The assumptions we make about a dataset when choosing to apply linear regression:
1. Linearity
	There is a linear relationship between y and x, such that it can be modelled by the equation $y = mx+b$
2. Homoscedasticity
	Equal Variance: There shouldn't be a cone type shape (increasing or decreasing) because it shows a dependance on dependent variable
3. Multivariate Normality
	Normality of error distribution. As we look at data points around regression line, we want to see a normal distribution.
4. Independence of observations, which includes no autocorrelation
	There really should be no pattern to data, as this indicates each variable is not truly independent
5. Lack of multicollinearity
	Whenever an independent variable is highly correlated with one or more of the other independent variables in a multiple regression equation - it undermines the statistical significance of an independent variable.
...and an extra check that there aren't outliers skewing the data.