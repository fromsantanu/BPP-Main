Chapter 4: Linear Regression Models
Simple Linear Regression
Simple linear regression is used to predict the value of one variable based on the value of another variable. The relationship is modeled using a straight line.

Example: Predicting Weight Based on Height
Let's use a simple dataset to demonstrate simple linear regression.

python
Copy code
import pandas as pd
import statsmodels.api as sm
import matplotlib.pyplot as plt

# Example dataset
data = {
    'Height': [150, 160, 170, 180, 190],
    'Weight': [50, 60, 70, 80, 90]
}
df = pd.DataFrame(data)

# Defining the predictor (X) and response (Y)
X = df['Height']
Y = df['Weight']

# Adding a constant to the predictor (X)
X = sm.add_constant(X)

# Fitting the regression model
model = sm.OLS(Y, X).fit()

# Summary of the model
print(model.summary())

# Plotting the regression line
plt.scatter(df['Height'], df['Weight'], color='blue')
plt.plot(df['Height'], model.predict(X), color='red')
plt.xlabel('Height')
plt.ylabel('Weight')
plt.title('Simple Linear Regression')
plt.show()
Multiple Linear Regression
Multiple linear regression is used to predict the value of one variable based on the values of two or more other variables.

Example: Predicting Price Based on Size and Location
Let's use a hypothetical dataset to demonstrate multiple linear regression.

python
Copy code
# Example dataset
data = {
    'Size': [1000, 1500, 2000, 2500, 3000],
    'Location': [1, 2, 3, 4, 5],
    'Price': [200, 250, 300, 350, 400]
}
df = pd.DataFrame(data)

# Defining the predictors (X) and response (Y)
X = df[['Size', 'Location']]
Y = df['Price']

# Adding a constant to the predictors (X)
X = sm.add_constant(X)

# Fitting the regression model
model = sm.OLS(Y, X).fit()

# Summary of the model
print(model.summary())
Model Diagnostics and Assumptions
After fitting a linear regression model, it is essential to check the model diagnostics and validate the assumptions.

Residual Analysis
Residuals are the differences between the observed and predicted values. Analyzing residuals helps in diagnosing the model.

python
Copy code
# Residuals
residuals = model.resid

# Plotting residuals
plt.scatter(model.fittedvalues, residuals)
plt.xlabel('Fitted Values')
plt.ylabel('Residuals')
plt.title('Residuals vs Fitted Values')
plt.axhline(0, color='red', linestyle='--')
plt.show()
Normality of Residuals
The residuals should be normally distributed. A Q-Q plot can help check this assumption.

python
Copy code
# Q-Q plot
sm.qqplot(residuals, line='45')
plt.title('Q-Q Plot')
plt.show()
Homoscedasticity
The residuals should have constant variance. A plot of residuals versus fitted values helps check this assumption.

python
Copy code
# Plotting residuals vs fitted values
plt.scatter(model.fittedvalues, residuals)
plt.xlabel('Fitted Values')
plt.ylabel('Residuals')
plt.title('Residuals vs Fitted Values')
plt.axhline(0, color='red', linestyle='--')
plt.show()
Independence of Residuals
Residuals should be independent of each other. The Durbin-Watson test can help check for autocorrelation.

python
Copy code
# Durbin-Watson test
from statsmodels.stats.stattools import durbin_watson

dw = durbin_watson(residuals)
print(f'Durbin-Watson statistic: {dw}')
Example: Complete Workflow
Here is a complete example that demonstrates simple linear regression, multiple linear regression, and model diagnostics.

python
Copy code
import pandas as pd
import statsmodels.api as sm
import matplotlib.pyplot as plt
from statsmodels.stats.stattools import durbin_watson

# Example dataset
data = {
    'Height': [150, 160, 170, 180, 190],
    'Weight': [50, 60, 70, 80, 90],
    'Size': [1000, 1500, 2000, 2500, 3000],
    'Location': [1, 2, 3, 4, 5],
    'Price': [200, 250, 300, 350, 400]
}
df = pd.DataFrame(data)

# Simple Linear Regression
X_simple = sm.add_constant(df['Height'])
Y_simple = df['Weight']
model_simple = sm.OLS(Y_simple, X_simple).fit()
print("Simple Linear Regression Summary:")
print(model_simple.summary())

# Multiple Linear Regression
X_multiple = sm.add_constant(df[['Size', 'Location']])
Y_multiple = df['Price']
model_multiple = sm.OLS(Y_multiple, X_multiple).fit()
print("Multiple Linear Regression Summary:")
print(model_multiple.summary())

# Residual Analysis for Multiple Linear Regression
residuals = model_multiple.resid

# Plotting residuals vs fitted values
plt.scatter(model_multiple.fittedvalues, residuals)
plt.xlabel('Fitted Values')
plt.ylabel('Residuals')
plt.title('Residuals vs Fitted Values')
plt.axhline(0, color='red', linestyle='--')
plt.show()

# Q-Q plot
sm.qqplot(residuals, line='45')
plt.title('Q-Q Plot')
plt.show()

# Durbin-Watson test
dw = durbin_watson(residuals)
print(f'Durbin-Watson statistic: {dw}')
In this chapter, we covered the basics of linear regression models, including simple linear regression and multiple linear regression. We also discussed model diagnostics and assumptions, which are crucial for validating and interpreting regression models.
