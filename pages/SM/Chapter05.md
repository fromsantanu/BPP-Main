# Chapter 5: Generalized Linear Models (GLM)

## Overview of GLMs
Generalized Linear Models (GLMs) are an extension of linear regression models that allow the dependent variable to have a distribution other than the normal distribution. GLMs consist of three components:

- Random Component: Specifies the distribution of the dependent variable (e.g., normal, binomial, Poisson).
- Systematic Component: Linear predictor which is a linear combination of the independent variables.
- Link Function: Connects the mean of the dependent variable to the linear predictor.

## GLM Formula

The general form of a GLM is:

$\[ g(\mu) = \mathbf{X}\beta \]$

Where:
- $\( g \)$ is the link function.
- $\( \mu \)$ is the mean of the dependent variable.
- $\( \mathbf{X} \)$ is the matrix of independent variables.
- $\( \beta \)$ is the vector of coefficients.

## Logistic Regression

Logistic regression is a type of GLM used when the dependent variable is binary (0 or 1). It uses the logit link function:

$\[ \text{logit}(\pi) = \log \left( \frac{\pi}{1 - \pi} \right) \]$

Where $\( \pi \)$ is the probability of the dependent variable being 1.

### Example: Predicting Binary Outcome
Let's use a hypothetical dataset to demonstrate logistic regression.

```python
import pandas as pd
import statsmodels.api as sm

# Example dataset
data = {
    'Hours_Studied': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    'Pass': [0, 0, 0, 0, 1, 0, 1, 1, 1, 1]
}
df = pd.DataFrame(data)

# Defining the predictor (X) and response (Y)
X = df['Hours_Studied']
Y = df['Pass']

# Adding a constant to the predictor (X)
X = sm.add_constant(X)

# Fitting the logistic regression model
model = sm.Logit(Y, X).fit()

# Summary of the model
print(model.summary())
```

### Plotting the Logistic Regression Curve
```python
import numpy as np
import matplotlib.pyplot as plt

# Predicting probabilities
X_new = np.linspace(0, 10, 100)
X_new = sm.add_constant(X_new)
predicted_probs = model.predict(X_new)

# Plotting
plt.scatter(df['Hours_Studied'], df['Pass'], color='blue', label='Data')
plt.plot(X_new[:, 1], predicted_probs, color='red', label='Logistic Regression')
plt.xlabel('Hours Studied')
plt.ylabel('Probability of Passing')
plt.title('Logistic Regression')
plt.legend()
plt.show()
```

## Poisson Regression

Poisson regression is used for count data, where the dependent variable represents the number of occurrences of an event. It uses the log link function:

$\[ \log(\mu) = \mathbf{X}\beta \]$

Where $\( \mu \)$ is the expected count.


### Example: Predicting Count Data
Let's use a hypothetical dataset to demonstrate Poisson regression.

```python
# Example dataset
data = {
    'Exposure': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    'Count': [0, 1, 3, 4, 5, 6, 8, 7, 10, 9]
}
df = pd.DataFrame(data)

# Defining the predictor (X) and response (Y)
X = df['Exposure']
Y = df['Count']

# Adding a constant to the predictor (X)
X = sm.add_constant(X)

# Fitting the Poisson regression model
model = sm.GLM(Y, X, family=sm.families.Poisson()).fit()

# Summary of the model
print(model.summary())
```

### Plotting the Poisson Regression Curve
```python
# Predicting counts
X_new = np.linspace(0, 10, 100)
X_new = sm.add_constant(X_new)
predicted_counts = model.predict(X_new)

# Plotting
plt.scatter(df['Exposure'], df['Count'], color='blue', label='Data')
plt.plot(X_new[:, 1], predicted_counts, color='red', label='Poisson Regression')
plt.xlabel('Exposure')
plt.ylabel('Count')
plt.title('Poisson Regression')
plt.legend()
plt.show()
```

## Example: Complete Workflow
Here is a complete example that demonstrates logistic regression and Poisson regression.

```python
import pandas as pd
import statsmodels.api as sm
import numpy as np
import matplotlib.pyplot as plt

# Logistic Regression Example
# Example dataset
data_logistic = {
    'Hours_Studied': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    'Pass': [0, 0, 0, 0, 1, 0, 1, 1, 1, 1]
}
df_logistic = pd.DataFrame(data_logistic)

# Defining the predictor (X) and response (Y)
X_logistic = df_logistic['Hours_Studied']
Y_logistic = df_logistic['Pass']

# Adding a constant to the predictor (X)
X_logistic = sm.add_constant(X_logistic)

# Fitting the logistic regression model
model_logistic = sm.Logit(Y_logistic, X_logistic).fit()
print("Logistic Regression Summary:")
print(model_logistic.summary())

# Predicting probabilities
X_new_logistic = np.linspace(0, 10, 100)
X_new_logistic = sm.add_constant(X_new_logistic)
predicted_probs_logistic = model_logistic.predict(X_new_logistic)

# Plotting Logistic Regression
plt.scatter(df_logistic['Hours_Studied'], df_logistic['Pass'], color='blue', label='Data')
plt.plot(X_new_logistic[:, 1], predicted_probs_logistic, color='red', label='Logistic Regression')
plt.xlabel('Hours Studied')
plt.ylabel('Probability of Passing')
plt.title('Logistic Regression')
plt.legend()
plt.show()

# Poisson Regression Example
# Example dataset
data_poisson = {
    'Exposure': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    'Count': [0, 1, 3, 4, 5, 6, 8, 7, 10, 9]
}
df_poisson = pd.DataFrame(data_poisson)

# Defining the predictor (X) and response (Y)
X_poisson = df_poisson['Exposure']
Y_poisson = df_poisson['Count']

# Adding a constant to the predictor (X)
X_poisson = sm.add_constant(X_poisson)

# Fitting the Poisson regression model
model_poisson = sm.GLM(Y_poisson, X_poisson, family=sm.families.Poisson()).fit()
print("Poisson Regression Summary:")
print(model_poisson.summary())

# Predicting counts
X_new_poisson = np.linspace(0, 10, 100)
X_new_poisson = sm.add_constant(X_new_poisson)
predicted_counts_poisson = model_poisson.predict(X_new_poisson)

# Plotting Poisson Regression
plt.scatter(df_poisson['Exposure'], df_poisson['Count'], color='blue', label='Data')
plt.plot(X_new_poisson[:, 1], predicted_counts_poisson, color='red', label='Poisson Regression')
plt.xlabel('Exposure')
plt.ylabel('Count')
plt.title('Poisson Regression')
plt.legend()
plt.show()
```

In this chapter, we covered the basics of Generalized Linear Models (GLMs), including logistic regression and Poisson regression. We provided examples to demonstrate how to fit these models using Python's statsmodels library, and how to interpret and visualize the results.
