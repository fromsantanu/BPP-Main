Chapter 11: Advanced Data Operations
11.1 Window Functions (Rolling, Expanding)
Window functions allow you to perform operations on a sliding window of data, which is useful for time series analysis and other applications.

Creating a sample DataFrame:

python
Copy code
import pandas as pd
import numpy as np

# Creating a sample DataFrame
data = {
    'Date': pd.date_range(start='2021-01-01', periods=10, freq='D'),
    'Value': np.random.randint(1, 100, 10)
}
df = pd.DataFrame(data)
print(df)
Rolling window:

python
Copy code
# Calculating rolling mean with a window size of 3
df['Rolling_Mean'] = df['Value'].rolling(window=3).mean()
print(df)

# Calculating rolling sum with a window size of 3
df['Rolling_Sum'] = df['Value'].rolling(window=3).sum()
print(df)
Expanding window:

python
Copy code
# Calculating expanding mean
df['Expanding_Mean'] = df['Value'].expanding().mean()
print(df)

# Calculating expanding sum
df['Expanding_Sum'] = df['Value'].expanding().sum()
print(df)
11.2 Multi-Indexing
Multi-indexing allows you to work with hierarchical indexing, enabling you to handle more complex data structures.

Creating a MultiIndex DataFrame:

python
Copy code
# Creating a sample MultiIndex DataFrame
arrays = [
    ['A', 'A', 'B', 'B'],
    ['one', 'two', 'one', 'two']
]
index = pd.MultiIndex.from_arrays(arrays, names=('Group', 'Subgroup'))
data = {'Value': [10, 20, 30, 40]}
df_multi = pd.DataFrame(data, index=index)
print(df_multi)
Accessing data with MultiIndex:

python
Copy code
# Accessing data for a specific group
print(df_multi.loc['A'])

# Accessing data for a specific subgroup
print(df_multi.loc[('A', 'one')])
Stacking and unstacking:

python
Copy code
# Unstacking the MultiIndex DataFrame
df_unstacked = df_multi.unstack()
print(df_unstacked)

# Stacking the DataFrame back
df_stacked = df_unstacked.stack()
print(df_stacked)
11.3 Working with Categorical Data
Categorical data is useful for representing a finite number of categories, which can improve performance and reduce memory usage.

Creating a DataFrame with categorical data:

python
Copy code
# Creating a sample DataFrame
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve'],
    'Department': ['HR', 'IT', 'HR', 'IT', 'Finance'],
    'Salary': [50000, 60000, 55000, 65000, 70000]
}
df = pd.DataFrame(data)
print(df)

# Converting 'Department' to a categorical column
df['Department'] = df['Department'].astype('category')
print(df)
print(df.dtypes)
Using categorical data:

python
Copy code
# Adding a new category
df['Department'] = df['Department'].cat.add_categories(['Marketing'])
print(df)

# Renaming categories
df['Department'] = df['Department'].cat.rename_categories({'IT': 'Information Technology'})
print(df)

# Removing unused categories
df['Department'] = df['Department'].cat.remove_unused_categories()
print(df)
Performing operations with categorical data:

python
Copy code
# Grouping by categorical data
grouped = df.groupby('Department').mean()
print(grouped)

# Sorting by categorical data
df_sorted = df.sort_values(by='Department')
print(df_sorted)
By the end of this chapter, you should be proficient in using advanced data operations in Pandas, including window functions, multi-indexing, and working with categorical data. These skills are essential for handling more complex data manipulation tasks and improving the efficiency of your data analysis workflows.
