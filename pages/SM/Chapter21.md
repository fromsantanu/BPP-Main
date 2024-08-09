# Chapter 21: Integration with Scikit-Learn

## Overview
This chapter focuses on integrating statsmodels with scikit-learn for hybrid modeling approaches. We will cover how to combine the strengths of both libraries to perform comprehensive data analysis and modeling.

## Combining statsmodels and Scikit-Learn
statsmodels provides detailed statistical tests and models, while scikit-learn is a powerful library for machine learning and model evaluation. Combining these two can leverage the strengths of both libraries.

### Example: Combining statsmodels and Scikit-Learn for Linear Regression
Let's use a hypothetical dataset to demonstrate combining statsmodels and scikit-learn for linear regression.

```python
import pandas as pd
import numpy as np
import statsmodels.api as sm
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score

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

# Splitting the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, Y, test_size=0.2, random_state=0)

# Using statsmodels for detailed regression analysis
X_train_sm = sm.add_constant(X_train)
model_sm = sm.OLS(y_train, X_train_sm).fit()
print(model_sm.summary())

# Using scikit-learn for model training and evaluation
model_sk = LinearRegression()
model_sk.fit(X_train, y_train)
y_pred = model_sk.predict(X_test)

# Evaluating the model
mse = mean_squared_error(y_test, y_pred)
r2 = r2_score(y_test, y_pred)
print(f'Mean Squared Error: {mse}')
print(f'R-squared: {r2}')
```

## Hybrid Modeling Approaches
Hybrid modeling approaches involve combining different types of models to improve performance. For example, you can use statsmodels for statistical modeling and scikit-learn for machine learning.

### Example: Hybrid Modeling with Logistic Regression
Let's use a hypothetical dataset to demonstrate hybrid modeling with logistic regression.

```python
import pandas as pd
import numpy as np
import statsmodels.api as sm
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import classification_report, roc_auc_score, roc_curve
import matplotlib.pyplot as plt

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

# Splitting the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, Y, test_size=0.2, random_state=0)

# Using statsmodels for detailed regression analysis
X_train_sm = sm.add_constant(X_train)
model_sm = sm.Logit(y_train, X_train_sm).fit()
print(model_sm.summary())

# Using scikit-learn for model training and evaluation
model_sk = LogisticRegression()
model_sk.fit(X_train, y_train)
y_pred = model_sk.predict(X_test)
y_pred_prob = model_sk.predict_proba(X_test)[:, 1]

# Evaluating the model
print(classification_report(y_test, y_pred))
roc_auc = roc_auc_score(y_test, y_pred_prob)
print(f'ROC AUC: {roc_auc}')

# ROC curve
fpr, tpr, _ = roc_curve(y_test, y_pred_prob)
plt.plot(fpr, tpr, label=f'ROC curve (area = {roc_auc:.2f})')
plt.plot([0, 1], [0, 1], linestyle='--')
plt.xlabel('False Positive Rate')
plt.ylabel('True Positive Rate')
plt.title('Receiver Operating Characteristic (ROC) Curve')
plt.legend(loc='lower right')
plt.show()
```

## Example: Complete Workflow
Here is a complete example that demonstrates combining statsmodels and scikit-learn for hybrid modeling approaches.

```python
import pandas as pd
import numpy as np
import statsmodels.api as sm
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression, LogisticRegression
from sklearn.metrics import mean_squared_error, r2_score, classification_report, roc_auc_score, roc_curve
import matplotlib.pyplot as plt

# Combining statsmodels and Scikit-Learn for Linear Regression
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

# Splitting the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, Y, test_size=0.2, random_state=0)

# Using statsmodels for detailed regression analysis
X_train_sm = sm.add_constant(X_train)
model_sm = sm.OLS(y_train, X_train_sm).fit()
print(model_sm.summary())

# Using scikit-learn for model training and evaluation
model_sk = LinearRegression()
model_sk.fit(X_train, y_train)
y_pred = model_sk.predict(X_test)

# Evaluating the model
mse = mean_squared_error(y_test, y_pred)
r2 = r2_score(y_test, y_pred)
print(f'Mean Squared Error: {mse}')
print(f'R-squared: {r2}')

# Hybrid Modeling with Logistic Regression
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

# Splitting the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, Y, test_size=0.2, random_state=0)

# Using statsmodels for detailed regression analysis
X_train_sm = sm.add_constant(X_train)
model_sm = sm.Logit(y_train, X_train_sm).fit()
print(model_sm.summary())

# Using scikit-learn for model training and evaluation
model_sk = LogisticRegression()
model_sk.fit(X_train, y_train)
y_pred = model_sk.predict(X_test)
y_pred_prob = model_sk.predict_proba(X_test)[:, 1]

# Evaluating the model
print(classification_report(y_test, y_pred))
roc_auc = roc_auc_score(y_test, y_pred_prob)
print(f'ROC AUC: {roc_auc}')

# ROC curve
fpr, tpr, _ = roc_curve(y_test, y_pred_prob)
plt.plot(fpr, tpr, label=f'ROC curve (area = {roc_auc:.2f})')
plt.plot([0, 1], [0, 1], linestyle='--')
plt.xlabel('False Positive Rate')
plt.ylabel('True Positive Rate')
plt.title('Receiver Operating Characteristic (ROC) Curve')
plt.legend(loc='lower right')
plt.show()
```

In this chapter, we covered the integration of statsmodels with scikit-learn, including combining the strengths of both libraries for hybrid modeling approaches. We provided examples to demonstrate how to perform these tasks using Python's Pandas, statsmodels, and scikit-learn libraries, and how to interpret the results.
