# Chapter 6: Data Cleaning

## 6.1 Handling Missing Data

### Creating a DataFrame with missing data:

```python
import pandas as pd
import numpy as np

data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve'],
    'Age': [25, np.nan, 35, 40, np.nan],
    'City': ['New York', 'Los Angeles', 'Chicago', np.nan, 'Phoenix']
}
df = pd.DataFrame(data)
print(df)
```

### Detecting missing data:

```python
# Detecting missing data
print(df.isnull())
```

### Dropping rows with missing data:

```python
# Dropping rows with any missing data
df_dropped = df.dropna()
print(df_dropped)
```

### Filling missing data:

```python
# Filling missing data with a specific value
df_filled = df.fillna({'Age': df['Age'].mean(), 'City': 'Unknown'})
print(df_filled)
```

### Forward fill (fill from previous value):

```python
# Forward fill missing data
df_ffill = df.fillna(method='ffill')
print(df_ffill)
```

### Backward fill (fill from next value):

```python
# Backward fill missing data
df_bfill = df.fillna(method='bfill')
print(df_bfill)
```

## 6.2 Removing Duplicates

### Creating a DataFrame with duplicates:

```python
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Alice'],
    'Age': [25, 30, 35, 40, 25],
    'City': ['New York', 'Los Angeles', 'Chicago', 'Houston', 'New York']
}
df = pd.DataFrame(data)
print(df)
```

### Removing duplicate rows:

```python
# Removing duplicate rows
df_no_duplicates = df.drop_duplicates()
print(df_no_duplicates)
```

### Removing duplicates based on specific columns:

```python
# Removing duplicates based on 'Name' column
df_no_duplicates_name = df.drop_duplicates(subset=['Name'])
print(df_no_duplicates_name)
```

## 6.3 Data Type Conversions

### Creating a DataFrame:

```python
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve'],
    'Age': ['25', '30', '35', '40', '45'],
    'Salary': ['50000', '60000', '70000', '80000', '90000']
}
df = pd.DataFrame(data)
print(df)
```

### Converting data types:

```python
# Converting 'Age' and 'Salary' to integers
df['Age'] = df['Age'].astype(int)
df['Salary'] = df['Salary'].astype(float)
print(df.dtypes)
print(df)
```

### Converting to datetime:

```python
# Adding a date column
df['Date'] = ['2021-01-01', '2021-02-01', '2021-03-01', '2021-04-01', '2021-05-01']
df['Date'] = pd.to_datetime(df['Date'])
print(df.dtypes)
print(df)
```

## 6.4 Renaming Columns and Indexes

### Creating a DataFrame:

```python
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve'],
    'Age': [25, 30, 35, 40, 45],
    'City': ['New York', 'Los Angeles', 'Chicago', 'Houston', 'Phoenix']
}
df = pd.DataFrame(data)
print(df)
```

### Renaming columns:

```python
# Renaming columns
df_renamed = df.rename(columns={'Name': 'Full Name', 'Age': 'Years', 'City': 'Location'})
print(df_renamed)
```

### Renaming indexes:

```python
# Setting 'Name' as index and renaming index
df_indexed = df.set_index('Name')
df_indexed = df_indexed.rename(index={'Alice': 'Alicia', 'Bob': 'Robert'})
print(df_indexed)
```

By the end of this chapter, you should be able to effectively clean your data by handling missing values, removing duplicates, converting data types, and renaming columns and indexes. These skills are essential for preparing data for analysis.
