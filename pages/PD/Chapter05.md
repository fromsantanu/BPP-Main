# Chapter 5: Data Inspection

## 5.1 Viewing Data (head, tail, sample)

### Viewing the first few rows:

```python
import pandas as pd

# Creating a sample DataFrame
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve'],
    'Age': [25, 30, 35, 40, 45],
    'City': ['New York', 'Los Angeles', 'Chicago', 'Houston', 'Phoenix']
}
df = pd.DataFrame(data)

# Viewing the first 5 rows
print(df.head())
```

### Viewing the last few rows:

```python
# Viewing the last 5 rows
print(df.tail())
```

### Viewing a random sample of rows:

```python
# Viewing a random sample of 3 rows
print(df.sample(3))
```

## 5.2 Getting DataFrame Information (info, describe)

### Getting a summary of the DataFrame:

```python
# Getting a summary of the DataFrame
print(df.info())
```

### Getting descriptive statistics:

```python
# Getting descriptive statistics
print(df.describe())
```

## 5.3 Data Selection and Filtering

### Selecting columns:

```python
# Selecting a single column
print(df['Name'])

# Selecting multiple columns
print(df[['Name', 'City']])
```

### Filtering rows based on a condition:

```python
# Filtering rows where Age is greater than 30
print(df[df['Age'] > 30])
```

### Filtering rows based on multiple conditions:

```python
# Filtering rows where Age is greater than 30 and City is 'Chicago'
print(df[(df['Age'] > 30) & (df['City'] == 'Chicago')])
```

## 5.4 Indexing and Selecting Data

### Setting an index:

```python
# Setting 'Name' as the index
df_indexed = df.set_index('Name')
print(df_indexed)
```

### Selecting data using loc:

```python
# Selecting a row by label
print(df_indexed.loc['Charlie'])

# Selecting multiple rows by label
print(df_indexed.loc[['Alice', 'David']])

# Selecting rows and columns by label
print(df_indexed.loc[['Alice', 'David'], ['Age', 'City']])
```

### Selecting data using iloc:

```python
# Selecting a row by position
print(df.iloc[2])

# Selecting multiple rows by position
print(df.iloc[1:3])

# Selecting rows and columns by position
print(df.iloc[1:3, 0:2])
```

By the end of this chapter, you should be adept at inspecting and understanding your DataFrame using various methods to view, filter, and select data. These skills are crucial for effective data analysis and manipulation in Pandas.

