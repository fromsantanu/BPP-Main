# Chapter 20: Integration with Pandas

## Overview
This chapter focuses on integrating statistical modeling with Pandas DataFrames. We will cover using statsmodels with Pandas DataFrames for data manipulation and model fitting.

## Using statsmodels with Pandas DataFrames
statsmodels is a powerful library for statistical modeling in Python. It integrates seamlessly with Pandas DataFrames, allowing for easy data manipulation and model fitting.

### Example: Linear Regression with Pandas DataFrames
Let's use a hypothetical dataset to demonstrate fitting a linear regression model using statsmodels with Pandas DataFrames.

```python
import pandas as pd
import numpy as np
import statsmodels.api as sm

# Creating a sample dataset
np.random.seed(0)
data = {
    'X1': np.random.randn(100),
    'X2': np.random.randn(100),
    'Y': np.random.randn(100) + 2 * np.random.randn(100)
}
df = pd.DataFrame(data)

# Defining the predictor variables (X) and response variable (Y)
X = df[['X1', 'X2']]
Y = df['Y']

# Adding a constant to the predictor variables
X = sm.add_constant(X)

# Fitting the linear regression model
model = sm.OLS(Y, X).fit()

# Summary of the model
print(model.summary())
```

## Data Manipulation and Model Fitting
Data manipulation is an essential step before fitting a model. Pandas provides powerful tools for data cleaning, transformation, and aggregation, which can be used in conjunction with statsmodels for model fitting.

### Example: Data Manipulation and Model Fitting
Let's use a hypothetical dataset to demonstrate data manipulation and fitting a logistic regression model using statsmodels.

```python
import pandas as pd
import numpy as np
import statsmodels.api as sm

# Creating a sample dataset
np.random.seed(0)
data = {
    'Age': np.random.randint(20, 80, 100),
    'BloodPressure': np.random.randint(90, 180, 100),
    'Cholesterol': np.random.randint(150, 300, 100),
    'Diabetes': np.random.choice([0, 1], 100),  # 0: No, 1: Yes
    'HeartDisease': np.random.choice([0, 1], 100)  # 0: No, 1: Yes
}
df = pd.DataFrame(data)

# Converting categorical variables
df['Diabetes'] = df['Diabetes'].astype('category')
df['HeartDisease'] = df['HeartDisease'].astype('category')

# Creating dummy variables for categorical predictors
df = pd.get_dummies(df, drop_first=True)

# Defining the predictor variables (X) and response variable (Y)
X = df[['Age', 'BloodPressure', 'Cholesterol', 'Diabetes_1']]
Y = df['HeartDisease_1']

# Adding a constant to the predictor variables
X = sm.add_constant(X)

# Fitting the logistic regression model
model = sm.Logit(Y, X).fit()

# Summary of the model
print(model.summary())
```

### Example: Data Aggregation and Model Fitting
Let's use a hypothetical dataset to demonstrate data aggregation and fitting a linear regression model using statsmodels.

```python
import pandas as pd
import numpy as np
import statsmodels.api as sm

# Creating a sample dataset
np.random.seed(0)
data = {
    'Group': np.random.choice(['A', 'B', 'C'], 100),
    'Value1': np.random.randn(100),
    'Value2': np.random.randn(100),
    'Outcome': np.random.randn(100)
}
df = pd.DataFrame(data)

# Aggregating data by group
grouped_df = df.groupby('Group').mean().reset_index()
print(grouped_df)

# Defining the predictor variables (X) and response variable (Y)
X = grouped_df[['Value1', 'Value2']]
Y = grouped_df['Outcome']

# Adding a constant to the predictor variables
X = sm.add_constant(X)

# Fitting the linear regression model
model = sm.OLS(Y, X).fit()

# Summary of the model
print(model.summary())
```

## Example: Complete Workflow
Here is a complete example that demonstrates using statsmodels with Pandas DataFrames for data manipulation and model fitting.

```python
import pandas as pd
import numpy as np
import statsmodels.api as sm

# Using statsmodels with Pandas DataFrames
# Creating a sample dataset
np.random.seed(0)
data = {
    'X1': np.random.randn(100),
    'X2': np.random.randn(100),
    'Y': np.random.randn(100) + 2 * np.random.randn(100)
}
df = pd.DataFrame(data)

# Defining the predictor variables (X) and response variable (Y)
X = df[['X1', 'X2']]
Y = df['Y']

# Adding a constant to the predictor variables
X = sm.add_constant(X)

# Fitting the linear regression model
model = sm.OLS(Y, X).fit()

# Summary of the model
print(model.summary())

# Data Manipulation and Model Fitting
# Creating a sample dataset
data = {
    'Age': np.random.randint(20, 80, 100),
    'BloodPressure': np.random.randint(90, 180, 100),
    'Cholesterol': np.random.randint(150, 300, 100),
    'Diabetes': np.random.choice([0, 1], 100),  # 0: No, 1: Yes
    'HeartDisease': np.random.choice([0, 1], 100)  # 0: No, 1: Yes
}
df = pd.DataFrame(data)

# Converting categorical variables
df['Diabetes'] = df['Diabetes'].astype('category')
df['HeartDisease'] = df['HeartDisease'].astype('category')

# Creating dummy variables for categorical predictors
df = pd.get_dummies(df, drop_first=True)

# Defining the predictor variables (X) and response variable (Y)
X = df[['Age', 'BloodPressure', 'Cholesterol', 'Diabetes_1']]
Y = df['HeartDisease_1']

# Adding a constant to the predictor variables
X = sm.add_constant(X)

# Fitting the logistic regression model
model = sm.Logit(Y, X).fit()

# Summary of the model
print(model.summary())

# Data Aggregation and Model Fitting
# Creating a sample dataset
data = {
    'Group': np.random.choice(['A', 'B', 'C'], 100),
    'Value1': np.random.randn(100),
    'Value2': np.random.randn(100),
    'Outcome': np.random.randn(100)
}
df = pd.DataFrame(data)

# Aggregating data by group
grouped_df = df.groupby('Group').mean().reset_index()
print(grouped_df)

# Defining the predictor variables (X) and response variable (Y)
X = grouped_df[['Value1', 'Value2']]
Y = grouped_df['Outcome']

# Adding a constant to the predictor variables
X = sm.add_constant(X)

# Fitting the linear regression model
model = sm.OLS(Y, X).fit()

# Summary of the model
print(model.summary())
```

In this chapter, we covered the integration of statsmodels with Pandas DataFrames, including data manipulation and model fitting. We provided examples to demonstrate how to perform these tasks using Python's Pandas and statsmodels libraries and how to interpret the results.
