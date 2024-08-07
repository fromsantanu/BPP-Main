Chapter 18: Case Studies in Healthcare and Epidemiology
Overview
This chapter focuses on applying statistical and data science techniques to healthcare and epidemiology. We will cover analyzing patient data, disease risk modeling, and survival analysis in clinical trials using real-world examples.

Analyzing Patient Data
Analyzing patient data involves understanding patterns, trends, and anomalies in the dataset. This can include exploratory data analysis (EDA), visualization, and basic statistical analysis.

Example: Analyzing Patient Data
Let's use a hypothetical patient dataset to perform exploratory data analysis and visualization.

python
Copy code
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Creating a sample patient dataset
np.random.seed(0)
data = {
    'Age': np.random.randint(20, 80, 100),
    'BloodPressure': np.random.randint(90, 180, 100),
    'Cholesterol': np.random.randint(150, 300, 100),
    'Diabetes': np.random.choice([0, 1], 100),  # 0: No, 1: Yes
    'HeartDisease': np.random.choice([0, 1], 100)  # 0: No, 1: Yes
}
df = pd.DataFrame(data)

# Basic statistical summary
print(df.describe())

# Visualizing the data
plt.figure(figsize=(10, 6))
sns.histplot(df['Age'], kde=True)
plt.title('Age Distribution')
plt.show()

plt.figure(figsize=(10, 6))
sns.boxplot(x='HeartDisease', y='BloodPressure', data=df)
plt.title('Blood Pressure by Heart Disease Status')
plt.show()

plt.figure(figsize=(10, 6))
sns.scatterplot(x='Cholesterol', y='BloodPressure', hue='Diabetes', data=df)
plt.title('Cholesterol vs Blood Pressure')
plt.show()
Disease Risk Modeling
Disease risk modeling involves predicting the likelihood of a disease based on various risk factors using statistical and machine learning models.

Example: Logistic Regression for Disease Risk Modeling
Let's use a hypothetical dataset to model the risk of heart disease based on age, blood pressure, cholesterol, and diabetes status.

python
Copy code
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import classification_report, roc_curve, auc

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

# Splitting the data into training and testing sets
X = df[['Age', 'BloodPressure', 'Cholesterol', 'Diabetes']]
y = df['HeartDisease']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=0)

# Fitting the logistic regression model
model = LogisticRegression()
model.fit(X_train, y_train)

# Making predictions
y_pred = model.predict(X_test)
y_pred_prob = model.predict_proba(X_test)[:, 1]

# Evaluating the model
print(classification_report(y_test, y_pred))

# ROC curve and AUC
fpr, tpr, _ = roc_curve(y_test, y_pred_prob)
roc_auc = auc(fpr, tpr)
plt.figure(figsize=(10, 6))
plt.plot(fpr, tpr, color='darkorange', lw=2, label='ROC curve (area = %0.2f)' % roc_auc)
plt.plot([0, 1], [0, 1], color='navy', lw=2, linestyle='--')
plt.xlabel('False Positive Rate')
plt.ylabel('True Positive Rate')
plt.title('Receiver Operating Characteristic (ROC) Curve')
plt.legend(loc='lower right')
plt.show()
Survival Analysis in Clinical Trials
Survival analysis is used to analyze the expected duration until one or more events happen, such as death or failure in clinical trials. It helps in understanding the time-to-event data.

Example: Kaplan-Meier Estimator for Survival Analysis
Let's use a hypothetical dataset to perform survival analysis using the Kaplan-Meier estimator.

python
Copy code
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from lifelines import Kaplan-MeierFitter

# Creating a sample clinical trial dataset
np.random.seed(0)
data = {
    'Time': np.random.exponential(scale=10, size=100),
    'Event': np.random.choice([0, 1], size=100)  # 0: Censored, 1: Event
}
df = pd.DataFrame(data)

# Kaplan-Meier estimator
kmf = Kaplan-MeierFitter()
kmf.fit(durations=df['Time'], event_observed=df['Event'])

# Plotting the survival function
kmf.plot_survival_function()
plt.title('Kaplan-Meier Estimate of Survival Function')
plt.xlabel('Time')
plt.ylabel('Survival Probability')
plt.show()
Example: Complete Workflow
Here is a complete example that demonstrates analyzing patient data, disease risk modeling, and survival analysis in clinical trials.

python
Copy code
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import classification_report, roc_curve, auc
from lifelines import Kaplan-MeierFitter

# Analyzing Patient Data
# Creating a sample patient dataset
np.random.seed(0)
data = {
    'Age': np.random.randint(20, 80, 100),
    'BloodPressure': np.random.randint(90, 180, 100),
    'Cholesterol': np.random.randint(150, 300, 100),
    'Diabetes': np.random.choice([0, 1], 100),  # 0: No, 1: Yes
    'HeartDisease': np.random.choice([0, 1], 100)  # 0: No, 1: Yes
}
df = pd.DataFrame(data)

# Basic statistical summary
print(df.describe())

# Visualizing the data
plt.figure(figsize=(10, 6))
sns.histplot(df['Age'], kde=True)
plt.title('Age Distribution')
plt.show()

plt.figure(figsize=(10, 6))
sns.boxplot(x='HeartDisease', y='BloodPressure', data=df)
plt.title('Blood Pressure by Heart Disease Status')
plt.show()

plt.figure(figsize=(10, 6))
sns.scatterplot(x='Cholesterol', y='BloodPressure', hue='Diabetes', data=df)
plt.title('Cholesterol vs Blood Pressure')
plt.show()

# Disease Risk Modeling
# Splitting the data into training and testing sets
X = df[['Age', 'BloodPressure', 'Cholesterol', 'Diabetes']]
y = df['HeartDisease']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=0)

# Fitting the logistic regression model
model = LogisticRegression()
model.fit(X_train, y_train)

# Making predictions
y_pred = model.predict(X_test)
y_pred_prob = model.predict_proba(X_test)[:, 1]

# Evaluating the model
print(classification_report(y_test, y_pred))

# ROC curve and AUC
fpr, tpr, _ = roc_curve(y_test, y_pred_prob)
roc_auc = auc(fpr, tpr)
plt.figure(figsize=(10, 6))
plt.plot(fpr, tpr, color='darkorange', lw=2, label='ROC curve (area = %0.2f)' % roc_auc)
plt.plot([0, 1], [0, 1], color='navy', lw=2, linestyle='--')
plt.xlabel('False Positive Rate')
plt.ylabel('True Positive Rate')
plt.title('Receiver Operating Characteristic (ROC) Curve')
plt.legend(loc='lower right')
plt.show()

# Survival Analysis in Clinical Trials
# Creating a sample clinical trial dataset
data = {
    'Time': np.random.exponential(scale=10, size=100),
    'Event': np.random.choice([0, 1], size=100)  # 0: Censored, 1: Event
}
df = pd.DataFrame(data)

# Kaplan-Meier estimator
kmf = Kaplan-MeierFitter()
kmf.fit(durations=df['Time'], event_observed=df['Event'])

# Plotting the survival function
kmf.plot_survival_function()
plt.title('Kaplan-Meier Estimate of Survival Function')
plt.xlabel('Time')
plt.ylabel('Survival Probability')
plt.show()
In this chapter, we covered the basics of case studies in healthcare and epidemiology, including analyzing patient data, disease risk modeling, and survival analysis in clinical trials. We provided examples to demonstrate how to perform these tasks using Python's libraries such as pandas, scikit-learn, and lifelines, and how to interpret the results.
