# Chapter 16: Model Diagnostics
## Overview of Model Diagnostics
Model diagnostics are crucial steps in evaluating the performance and validity of statistical models. They help in identifying potential issues such as non-linearity, multicollinearity, heteroscedasticity, and other violations of model assumptions.

## Residual Analysis
Residual analysis involves examining the residuals (the differences between observed and predicted values) to check for patterns that might indicate problems with the model.

### Example: Residual Analysis
Let's use a hypothetical dataset to demonstrate residual analysis.

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import statsmodels.api as sm

# Creating a sample dataset
np.random.seed(0)
X = np.random.randn(100)
Y = 2.5 * X + np.random.randn(100) * 0.5
X = sm.add_constant(X)  # Adds a constant term to the predictor

# Fitting a linear regression model
model = sm.OLS(Y, X).fit()

# Getting the residuals
residuals = model.resid

# Plotting the residuals
plt.scatter(model.fittedvalues, residuals)
plt.axhline(y=0, color='r', linestyle='--')
plt.xlabel('Fitted Values')
plt.ylabel('Residuals')
plt.title('Residuals vs Fitted Values')
plt.show()

# Q-Q plot
sm.qqplot(residuals, line='45')
plt.title('Q-Q Plot')
plt.show()
```

## Multicollinearity Detection
Multicollinearity occurs when two or more predictor variables in a regression model are highly correlated, which can affect the stability and interpretation of the model coefficients.

### Example: Multicollinearity Detection
Let's use a hypothetical dataset to demonstrate multicollinearity detection using Variance Inflation Factor (VIF).

```python
from statsmodels.stats.outliers_influence import variance_inflation_factor

# Creating a sample dataset
np.random.seed(0)
X1 = np.random.randn(100)
X2 = X1 + np.random.randn(100) * 0.01  # Highly correlated with X1
X3 = np.random.randn(100)
Y = 2.5 * X1 + 1.5 * X2 + np.random.randn(100) * 0.5

# Creating a DataFrame
df = pd.DataFrame({'X1': X1, 'X2': X2, 'X3': X3, 'Y': Y})

# Adding a constant term for VIF calculation
X = sm.add_constant(df[['X1', 'X2', 'X3']])

# Calculating VIF for each predictor
vif_data = pd.DataFrame()
vif_data['Feature'] = X.columns
vif_data['VIF'] = [variance_inflation_factor(X.values, i) for i in range(X.shape[1])]
print(vif_data)
```

## Heteroscedasticity Tests
Heteroscedasticity occurs when the variance of the residuals is not constant across all levels of the independent variable(s), which violates the assumption of homoscedasticity in linear regression models.

### Example: Heteroscedasticity Tests
Let's use a hypothetical dataset to demonstrate heteroscedasticity detection using the Breusch-Pagan test and the White test.

```python
from statsmodels.stats.diagnostic import het_breuschpagan, het_white

# Creating a sample dataset
np.random.seed(0)
X = np.random.randn(100)
Y = 2.5 * X + np.random.randn(100) * 0.5
X = sm.add_constant(X)  # Adds a constant term to the predictor

# Fitting a linear regression model
model = sm.OLS(Y, X).fit()

# Performing the Breusch-Pagan test
bp_test = het_breuschpagan(model.resid, model.model.exog)
print(f"Breusch-Pagan test results: LM stat = {bp_test[0]}, p-value = {bp_test[1]}, F stat = {bp_test[2]}, F p-value = {bp_test[3]}")

# Performing the White test
white_test = het_white(model.resid, model.model.exog)
print(f"White test results: LM stat = {white_test[0]}, p-value = {white_test[1]}, F stat = {white_test[2]}, F p-value = {white_test[3]}")
```

## Example: Complete Workflow
Here is a complete example that demonstrates residual analysis, multicollinearity detection, and heteroscedasticity tests.

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import statsmodels.api as sm
from statsmodels.stats.outliers_influence import variance_inflation_factor
from statsmodels.stats.diagnostic import het_breuschpagan, het_white

# Residual Analysis Example
# Creating a sample dataset
np.random.seed(0)
X_resid = np.random.randn(100)
Y_resid = 2.5 * X_resid + np.random.randn(100) * 0.5
X_resid = sm.add_constant(X_resid)  # Adds a constant term to the predictor

# Fitting a linear regression model
model_resid = sm.OLS(Y_resid, X_resid).fit()

# Getting the residuals
residuals = model_resid.resid

# Plotting the residuals
plt.scatter(model_resid.fittedvalues, residuals)
plt.axhline(y=0, color='r', linestyle='--')
plt.xlabel('Fitted Values')
plt.ylabel('Residuals')
plt.title('Residuals vs Fitted Values')
plt.show()

# Q-Q plot
sm.qqplot(residuals, line='45')
plt.title('Q-Q Plot')
plt.show()

# Multicollinearity Detection Example
# Creating a sample dataset
X1 = np.random.randn(100)
X2 = X1 + np.random.randn(100) * 0.01  # Highly correlated with X1
X3 = np.random.randn(100)
Y = 2.5 * X1 + 1.5 * X2 + np.random.randn(100) * 0.5

# Creating a DataFrame
df_multi = pd.DataFrame({'X1': X1, 'X2': X2, 'X3': X3, 'Y': Y})

# Adding a constant term for VIF calculation
X = sm.add_constant(df_multi[['X1', 'X2', 'X3']])

# Calculating VIF for each predictor
vif_data = pd.DataFrame()
vif_data['Feature'] = X.columns
vif_data['VIF'] = [variance_inflation_factor(X.values, i) for i in range(X.shape[1])]
print("VIF Data:")
print(vif_data)

# Heteroscedasticity Tests Example
# Creating a sample dataset
X_het = np.random.randn(100)
Y_het = 2.5 * X_het + np.random.randn(100) * 0.5
X_het = sm.add_constant(X_het)  # Adds a constant term to the predictor

# Fitting a linear regression model
model_het = sm.OLS(Y_het, X_het).fit()

# Performing the Breusch-Pagan test
bp_test = het_breuschpagan(model_het.resid, model_het.model.exog)
print(f"Breusch-Pagan test results: LM stat = {bp_test[0]}, p-value = {bp_test[1]}, F stat = {bp_test[2]}, F p-value = {bp_test[3]}")

# Performing the White test
white_test = het_white(model_het.resid, model_het.model.exog)
print(f"White test results: LM stat = {white_test[0]}, p-value = {white_test[1]}, F stat = {white_test[2]}, F p-value = {white_test[3]}")
```

In this chapter, we covered the basics of model diagnostics, including residual analysis, multicollinearity detection, and heteroscedasticity tests. We provided examples to demonstrate how to perform these diagnostics using Python's statsmodels library and how to interpret the results.
