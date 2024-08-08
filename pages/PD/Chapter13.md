# Chapter 13: Case Studies and Real-World Applications

## 13.1 Practical Examples and Case Studies in Healthcare and Epidemiology

### Example 1: Analyzing Hospital Admission Data

#### Creating a sample DataFrame:

```python
import pandas as pd

# Sample data for hospital admissions
data = {
    'PatientID': [1, 2, 3, 4, 5],
    'Age': [34, 55, 67, 45, 23],
    'Gender': ['F', 'M', 'F', 'M', 'F'],
    'AdmissionDate': ['2023-01-10', '2023-02-14', '2023-03-20', '2023-04-22', '2023-05-18'],
    'DischargeDate': ['2023-01-15', '2023-02-20', '2023-03-25', '2023-04-30', '2023-05-25'],
    'Diagnosis': ['Pneumonia', 'Stroke', 'Heart Attack', 'Fracture', 'Appendicitis']
}
df = pd.DataFrame(data)

# Converting date columns to datetime
df['AdmissionDate'] = pd.to_datetime(df['AdmissionDate'])
df['DischargeDate'] = pd.to_datetime(df['DischargeDate'])
print(df)
```

#### Calculating length of stay:

```python
# Calculating the length of stay
df['LengthOfStay'] = (df['DischargeDate'] - df['AdmissionDate']).dt.days
print(df)
```

#### Analyzing the average length of stay by diagnosis:

```python
# Grouping by diagnosis and calculating average length of stay
avg_length_of_stay = df.groupby('Diagnosis')['LengthOfStay'].mean()
print(avg_length_of_stay)
```

### Example 2: Monitoring Disease Incidence Over Time

#### Creating a sample DataFrame:

```python
# Sample data for disease incidence
data = {
    'Date': pd.date_range(start='2023-01-01', periods=100, freq='D'),
    'Incidence': [5, 6, 8, 5, 7, 6, 8, 7, 9, 10] * 10
}
df = pd.DataFrame(data)
print(df)
```

#### Plotting disease incidence over time:

```python
# Plotting disease incidence over time
df.plot(x='Date', y='Incidence', kind='line', title='Disease Incidence Over Time')
plt.xlabel('Date')
plt.ylabel('Number of Cases')
plt.show()
```

#### Resampling data to weekly incidence:

```python
# Resampling data to weekly incidence
df_weekly = df.resample('W', on='Date').sum()
print(df_weekly)

# Plotting weekly incidence
df_weekly.plot(y='Incidence', kind='line', title='Weekly Disease Incidence')
plt.xlabel('Week')
plt.ylabel('Number of Cases')
plt.show()
```

## 13.2 End-to-End Data Analysis Projects

### Project: Analyzing and Visualizing Dengue Fever Outbreak

#### Step 1: Data Collection

##### Creating a sample DataFrame:

```python
# Sample data for dengue fever cases
data = {
    'Date': pd.date_range(start='2023-01-01', periods=200, freq='D'),
    'Region': ['North', 'South', 'East', 'West'] * 50,
    'Cases': [15, 20, 25, 10, 18, 22, 27, 12] * 25
}
df = pd.DataFrame(data)
print(df)
```

##### Step 2: Data Cleaning

```python
# Checking for missing values
print(df.isnull().sum())

# No missing values in this sample dataset
```

##### Step 3: Data Analysis

###### Aggregating data by region and month:

```python
# Adding a month column
df['Month'] = df['Date'].dt.to_period('M')

# Grouping by region and month
monthly_cases = df.groupby(['Region', 'Month'])['Cases'].sum().reset_index()
print(monthly_cases)
```

##### Step 4: Data Visualization

###### Plotting monthly cases by region:

```python
# Plotting monthly cases by region
import matplotlib.pyplot as plt

fig, ax = plt.subplots()
for region in monthly_cases['Region'].unique():
    region_data = monthly_cases[monthly_cases['Region'] == region]
    ax.plot(region_data['Month'].astype(str), region_data['Cases'], label=region)

ax.set_title('Monthly Dengue Fever Cases by Region')
ax.set_xlabel('Month')
ax.set_ylabel('Number of Cases')
ax.legend()
plt.xticks(rotation=45)
plt.show()
```

##### Step 5: Reporting

###### Generating a summary report:

```python
# Summary report
total_cases = df['Cases'].sum()
print(f'Total Dengue Fever Cases: {total_cases}')

cases_by_region = df.groupby('Region')['Cases'].sum()
print('Cases by Region:')
print(cases_by_region)
```

###### Generating insights and recommendations:

```python
# Insights and recommendations
print("Insights:")
print("1. The highest number of cases occurred in the East region.")
print("2. There is a noticeable increase in cases during the mid-year months.")

print("\nRecommendations:")
print("1. Increase awareness and preventive measures in the East region.")
print("2. Implement mosquito control programs before the peak months.")
```

By the end of this chapter, you should be able to conduct complete data analysis projects from data collection to reporting. These real-world applications and case studies in healthcare and epidemiology will help you apply your Pandas skills to meaningful data analysis tasks.
