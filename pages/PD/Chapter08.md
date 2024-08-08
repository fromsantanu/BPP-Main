# Chapter 8: Data Aggregation and Grouping

## 8.1 GroupBy Operations
The groupby method in Pandas is used to split the data into groups based on some criteria and then apply a function to each group independently.

### Creating a DataFrame:

```python
import pandas as pd

data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve', 'Frank'],
    'Department': ['HR', 'IT', 'HR', 'IT', 'Finance', 'Finance'],
    'Salary': [50000, 60000, 55000, 65000, 70000, 72000],
    'Age': [25, 30, 35, 40, 45, 50]
}
df = pd.DataFrame(data)
print(df)
```

### Grouping by a single column:

```python
# Grouping by 'Department'
grouped = df.groupby('Department')
print(grouped)
```

### Iterating through groups:

```python
# Iterating through groups
for name, group in grouped:
    print(name)
    print(group)
```

## 8.2 Aggregation Functions
Aggregation functions allow you to compute summary statistics for each group.

### Using built-in aggregation functions:

```python
# Getting the mean salary by department
mean_salary = grouped['Salary'].mean()
print(mean_salary)

# Getting the sum of salaries by department
sum_salary = grouped['Salary'].sum()
print(sum_salary)
```

### Using multiple aggregation functions:

```python
# Applying multiple aggregation functions
agg_salary = grouped['Salary'].agg(['mean', 'sum', 'min', 'max'])
print(agg_salary)
```

## 8.3 Transformation and Filtration
Transformation functions allow you to perform operations on each group and return a DataFrame with the same shape.

### Applying transformations:

```python
# Normalizing salary within each department
normalized_salary = grouped['Salary'].transform(lambda x: (x - x.mean()) / x.std())
print(normalized_salary)
```

### Filtration functions allow you to filter out groups based on a condition.

#### Filtering groups:

```python
# Filtering departments where the average salary is greater than 60000
filtered_groups = grouped.filter(lambda x: x['Salary'].mean() > 60000)
print(filtered_groups)
```

## 8.4 Applying Custom Functions with apply
The apply method allows you to apply custom functions to each group and combine the results into a DataFrame.

### Applying custom functions:

```python
# Defining a custom function to get the range of salaries
def salary_range(group):
    return group['Salary'].max() - group['Salary'].min()

# Applying the custom function to each group
salary_ranges = grouped.apply(salary_range)
print(salary_ranges)
```

### Applying custom functions and returning DataFrame:

```python
# Defining a custom function to return a DataFrame
def summarize(group):
    return pd.DataFrame({
        'count': [group['Salary'].count()],
        'mean': [group['Salary'].mean()],
        'std': [group['Salary'].std()]
    })

# Applying the custom function and returning a DataFrame
summary = grouped.apply(summarize).reset_index(level=1, drop=True)
print(summary)
```

By the end of this chapter, you should be able to effectively use Pandas' grouping and aggregation functions to analyze and summarize your data. These skills are essential for performing complex data analysis tasks.
