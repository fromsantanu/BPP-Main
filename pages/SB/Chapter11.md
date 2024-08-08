# Case Studies in Healthcare and Epidemiology
This chapter focuses on practical applications of Seaborn and Matplotlib for visualizing patient data, analyzing disease spread, and creating custom visualizations for medical research. These case studies will demonstrate how to leverage data visualization tools to gain insights and make data-driven decisions in healthcare and epidemiology.

## Visualizing Patient Data
### Case Study 1: Visualizing Blood Pressure Data
Blood pressure data is crucial for monitoring patient health. Let's visualize systolic and diastolic blood pressure readings over time for a group of patients.

```python
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd

# Sample data for blood pressure readings
data = {
    "Patient ID": [1, 1, 1, 2, 2, 2, 3, 3, 3],
    "Date": pd.date_range(start="2021-01-01", periods=3).tolist() * 3,
    "Systolic": [120, 125, 130, 140, 135, 145, 150, 155, 160],
    "Diastolic": [80, 85, 90, 95, 90, 100, 105, 110, 115]
}

df = pd.DataFrame(data)

# Create a line plot for systolic and diastolic blood pressure
plt.figure(figsize=(12, 6))
sns.lineplot(data=df, x="Date", y="Systolic", hue="Patient ID", marker="o", label="Systolic")
sns.lineplot(data=df, x="Date", y="Diastolic", hue="Patient ID", marker="o", linestyle="--", label="Diastolic")
plt.title("Blood Pressure Readings Over Time")
plt.xlabel("Date")
plt.ylabel("Blood Pressure (mmHg)")
plt.legend(title="Blood Pressure Type")
plt.show()
```

## Analyzing Disease Spread
### Case Study 2: Analyzing COVID-19 Spread
Understanding the spread of infectious diseases, such as COVID-19, is essential for public health planning and response. Let's visualize the number of COVID-19 cases over time in different regions.

```python
# Sample data for COVID-19 cases
data = {
    "Date": pd.date_range(start="2020-01-01", periods=10),
    "Region": ["North", "South", "East", "West", "North", "South", "East", "West", "North", "South"],
    "Cases": [100, 200, 150, 300, 400, 500, 450, 600, 700, 800]
}

df = pd.DataFrame(data)

# Create a line plot for COVID-19 cases over time
plt.figure(figsize=(12, 6))
sns.lineplot(data=df, x="Date", y="Cases", hue="Region", marker="o")
plt.title("COVID-19 Cases Over Time by Region")
plt.xlabel("Date")
plt.ylabel("Number of Cases")
plt.legend(title="Region")
plt.show()
```

## Custom Visualizations for Medical Research
### Case Study 3: Visualizing Clinical Trial Results
Clinical trials generate a vast amount of data that need to be visualized effectively to communicate findings. Let's create a custom visualization to compare the effectiveness of two treatments over time.

```python
# Sample data for clinical trial results
data = {
    "Week": list(range(1, 11)) * 2,
    "Treatment": ["A"] * 10 + ["B"] * 10,
    "Response Rate": [0.5, 0.55, 0.6, 0.62, 0.65, 0.68, 0.7, 0.72, 0.75, 0.78, 
                      0.4, 0.45, 0.5, 0.55, 0.6, 0.65, 0.68, 0.7, 0.73, 0.75]
}

df = pd.DataFrame(data)

# Create a line plot for treatment response rates over time
plt.figure(figsize=(12, 6))
sns.lineplot(data=df, x="Week", y="Response Rate", hue="Treatment", marker="o")
plt.title("Clinical Trial Response Rates Over Time")
plt.xlabel("Week")
plt.ylabel("Response Rate")
plt.legend(title="Treatment")
plt.show()
```

## Combining Visualizations for Comprehensive Analysis
### Case Study 4: Dashboard for Patient Monitoring
Let's create a comprehensive dashboard for monitoring patient data, including blood pressure readings, heart rate, and temperature.

```python
# Sample data for patient monitoring
data = {
    "Patient ID": [1, 1, 1, 2, 2, 2, 3, 3, 3],
    "Date": pd.date_range(start="2021-01-01", periods=3).tolist() * 3,
    "Systolic": [120, 125, 130, 140, 135, 145, 150, 155, 160],
    "Diastolic": [80, 85, 90, 95, 90, 100, 105, 110, 115],
    "Heart Rate": [70, 72, 75, 78, 76, 80, 85, 88, 90],
    "Temperature": [98.6, 99.1, 99.5, 98.7, 99.0, 99.3, 98.9, 99.2, 99.6]
}

df = pd.DataFrame(data)

# Create a figure with subplots
fig, ax = plt.subplots(2, 2, figsize=(14, 12))

# Subplot 1: Systolic Blood Pressure
sns.lineplot(data=df, x="Date", y="Systolic", hue="Patient ID", marker="o", ax=ax[0, 0])
ax[0, 0].set_title("Systolic Blood Pressure Over Time")
ax[0, 0].set_xlabel("Date")
ax[0, 0].set_ylabel("Systolic (mmHg)")

# Subplot 2: Diastolic Blood Pressure
sns.lineplot(data=df, x="Date", y="Diastolic", hue="Patient ID", marker="o", ax=ax[0, 1])
ax[0, 1].set_title("Diastolic Blood Pressure Over Time")
ax[0, 1].set_xlabel("Date")
ax[0, 1].set_ylabel("Diastolic (mmHg)")

# Subplot 3: Heart Rate
sns.lineplot(data=df, x="Date", y="Heart Rate", hue="Patient ID", marker="o", ax=ax[1, 0])
ax[1, 0].set_title("Heart Rate Over Time")
ax[1, 0].set_xlabel("Date")
ax[1, 0].set_ylabel("Heart Rate (bpm)")

# Subplot 4: Temperature
sns.lineplot(data=df, x="Date", y="Temperature", hue="Patient ID", marker="o", ax=ax[1, 1])
ax[1, 1].set_title("Temperature Over Time")
ax[1, 1].set_xlabel("Date")
ax[1, 1].set_ylabel("Temperature (°F)")

# Adjust layout
plt.tight_layout()
plt.suptitle("Patient Monitoring Dashboard", y=1.02)
plt.show()
```

## Conclusion
Visualization plays a crucial role in healthcare and epidemiology by providing insights into patient data, disease spread, and clinical trial results. By leveraging Seaborn and Matplotlib, you can create detailed and informative visualizations to enhance data analysis and support decision-making in medical research and public health. This chapter covered various case studies, demonstrating the practical applications of these visualization tools in real-world healthcare scenarios.
