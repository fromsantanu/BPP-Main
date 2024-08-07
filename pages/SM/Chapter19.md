Chapter 19: Project Tutorials
Overview
This chapter focuses on end-to-end data analysis projects, integrating data analysis with visualization, and reporting and interpreting results. We will walk through a complete project using a hypothetical dataset to demonstrate these concepts.

End-to-End Data Analysis Projects
End-to-end data analysis involves several steps: data collection, data cleaning, exploratory data analysis, modeling, and validation. Let's walk through these steps using a hypothetical dataset.

Example: End-to-End Data Analysis
Step 1: Data Collection
For this example, we'll create a synthetic dataset.

python
Copy code
import pandas as pd
import numpy as np

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
print(df.head())
Step 2: Data Cleaning
Cleaning data involves handling missing values, duplicates, and incorrect data types.

python
Copy code
# Checking for missing values
print(df.isnull().sum())

# Checking for duplicates
print(df.duplicated().sum())

# Converting categorical variables
df['Diabetes'] = df['Diabetes'].astype('category')
df['HeartDisease'] = df['HeartDisease'].astype('category')

print(df.info())
Step 3: Exploratory Data Analysis
Exploratory data analysis (EDA) involves summarizing the main characteristics of the data using statistical graphics and plots.

python
Copy code
import matplotlib.pyplot as plt
import seaborn as sns

# Summary statistics
print(df.describe())

# Histograms
plt.figure(figsize=(10, 6))
sns.histplot(df['Age'], kde=True)
plt.title('Age Distribution')
plt.show()

# Box plots
plt.figure(figsize=(10, 6))
sns.boxplot(x='HeartDisease', y='BloodPressure', data=df)
plt.title('Blood Pressure by Heart Disease Status')
plt.show()

# Scatter plots
plt.figure(figsize=(10, 6))
sns.scatterplot(x='Cholesterol', y='BloodPressure', hue='Diabetes', data=df)
plt.title('Cholesterol vs Blood Pressure')
plt.show()
Step 4: Modeling
Modeling involves training a machine learning or statistical model to predict outcomes.

python
Copy code
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import classification_report, roc_curve, auc

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
Integrating Data Analysis with Visualization
Integrating data analysis with visualization helps in better understanding and communicating the results.

Example: Integrating Data Analysis with Visualization
We will create visualizations that complement our data analysis.

python
Copy code
# Visualizing model coefficients
coefficients = pd.DataFrame(model.coef_.T, index=X.columns, columns=['Coefficient'])
coefficients.plot(kind='bar', legend=False)
plt.title('Logistic Regression Coefficients')
plt.show()

# Plotting a confusion matrix
from sklearn.metrics import confusion_matrix
import seaborn as sns

cm = confusion_matrix(y_test, y_pred)
sns.heatmap(cm, annot=True, fmt='d', cmap='Blues', xticklabels=['No Heart Disease', 'Heart Disease'], yticklabels=['No Heart Disease', 'Heart Disease'])
plt.xlabel('Predicted')
plt.ylabel('Actual')
plt.title('Confusion Matrix')
plt.show()
Reporting and Interpreting Results
Reporting and interpreting results involves summarizing the findings in a clear and concise manner, often using visualizations to support the conclusions.

Example: Reporting and Interpreting Results
python
Copy code
# Summary of findings
print("Summary of Findings:")
print(f"Mean Age: {df['Age'].mean()}")
print(f"Percentage of Patients with Diabetes: {df['Diabetes'].mean() * 100:.2f}%")
print(f"Percentage of Patients with Heart Disease: {df['HeartDisease'].mean() * 100:.2f}%")
print(f"Model Accuracy: {model.score(X_test, y_test) * 100:.2f}%")

# Highlighting important findings
plt.figure(figsize=(10, 6))
sns.boxplot(x='HeartDisease', y='Cholesterol', data=df)
plt.title('Cholesterol Levels by Heart Disease Status')
plt.show()

# Reporting on ROC AUC
print(f'ROC AUC: {roc_auc:.2f}')
Example: Complete Workflow
Here is a complete example that demonstrates end-to-end data analysis, integrating data analysis with visualization, and reporting and interpreting results.

python
Copy code
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import classification_report, roc_curve, auc, confusion_matrix

# End-to-End Data Analysis
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

# Data Cleaning
df['Diabetes'] = df['Diabetes'].astype('category')
df['HeartDisease'] = df['HeartDisease'].astype('category')
print(df.info())

# Exploratory Data Analysis
print(df.describe())

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

# Modeling
X = df[['Age', 'BloodPressure', 'Cholesterol', 'Diabetes']]
y = df['HeartDisease']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=0)

model = LogisticRegression()
model.fit(X_train, y_train)

y_pred = model.predict(X_test)
y_pred_prob = model.predict_proba(X_test)[:, 1]

print(classification_report(y_test, y_pred))

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

# Integrating Data Analysis with Visualization
coefficients = pd.DataFrame(model.coef_.T, index=X.columns, columns=['Coefficient'])
coefficients.plot(kind='bar', legend=False)
plt.title('Logistic Regression Coefficients')
plt.show()

cm = confusion_matrix(y_test, y_pred)
sns.heatmap(cm, annot=True, fmt='d', cmap='Blues', xticklabels=['No Heart Disease', 'Heart Disease'], yticklabels=['No Heart Disease', 'Heart Disease'])
plt.xlabel('Predicted')
plt.ylabel('Actual')
plt.title('Confusion Matrix')
plt.show()

# Reporting and Interpreting Results
print("Summary of Findings:")
print(f"Mean Age: {df['Age'].mean()}")
print(f"Percentage of Patients with Diabetes: {df['Diabetes'].mean() * 100:.2f}%")
print(f"Percentage of Patients with Heart Disease: {df['HeartDisease'].mean() * 100:.2f}%")
print(f"Model Accuracy: {model.score(X_test, y_test) * 100:.2f}%")

plt.figure(figsize=(10, 6))
sns.boxplot(x='HeartDisease', y='Cholesterol', data=df)
plt.title('Cholesterol Levels by Heart Disease Status')
plt.show()

print(f'ROC AUC: {roc_auc:.2f}')
In this chapter, we covered end-to-end data analysis projects, integrating data analysis with visualization, and reporting and interpreting results. We provided examples to demonstrate how to perform these tasks using Python's pandas, scikit-learn, and seaborn libraries, and how to present the findings effectively.
