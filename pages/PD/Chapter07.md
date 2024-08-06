Chapter 7: Data Transformation
7.1 Sorting Data
Creating a DataFrame:

python
Copy code
import pandas as pd

data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve'],
    'Age': [25, 30, 35, 40, 45],
    'City': ['New York', 'Los Angeles', 'Chicago', 'Houston', 'Phoenix']
}
df = pd.DataFrame(data)
print(df)
Sorting by a single column:

python
Copy code
# Sorting by Age
df_sorted_age = df.sort_values(by='Age')
print(df_sorted_age)
Sorting by multiple columns:

python
Copy code
# Sorting by City and then by Age
df_sorted_city_age = df.sort_values(by=['City', 'Age'])
print(df_sorted_city_age)
Sorting in descending order:

python
Copy code
# Sorting by Age in descending order
df_sorted_desc = df.sort_values(by='Age', ascending=False)
print(df_sorted_desc)
7.2 DataFrame Merging and Joining
Creating DataFrames to merge:

python
Copy code
data1 = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35]
}
data2 = {
    'Name': ['Alice', 'Bob', 'David'],
    'City': ['New York', 'Los Angeles', 'Houston']
}
df1 = pd.DataFrame(data1)
df2 = pd.DataFrame(data2)
print(df1)
print(df2)
Merging DataFrames:

python
Copy code
# Merging on 'Name' column
df_merged = pd.merge(df1, df2, on='Name')
print(df_merged)
Merging with different join types:

python
Copy code
# Inner join (default)
df_inner = pd.merge(df1, df2, on='Name', how='inner')
print(df_inner)

# Outer join
df_outer = pd.merge(df1, df2, on='Name', how='outer')
print(df_outer)

# Left join
df_left = pd.merge(df1, df2, on='Name', how='left')
print(df_left)

# Right join
df_right = pd.merge(df1, df2, on='Name', how='right')
print(df_right)
7.3 Concatenation
Creating DataFrames to concatenate:

python
Copy code
data3 = {
    'Name': ['Alice', 'Bob'],
    'Age': [25, 30]
}
data4 = {
    'Name': ['Charlie', 'David'],
    'Age': [35, 40]
}
df3 = pd.DataFrame(data3)
df4 = pd.DataFrame(data4)
print(df3)
print(df4)
Concatenating DataFrames:

python
Copy code
# Concatenating along rows (default)
df_concat = pd.concat([df3, df4])
print(df_concat)

# Concatenating along columns
df_concat_col = pd.concat([df3, df4], axis=1)
print(df_concat_col)
7.4 Pivot Tables and Crosstab
Creating a DataFrame for pivot tables:

python
Copy code
data_pivot = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eve'],
    'Age': [25, 30, 35, 40, 45],
    'City': ['New York', 'Los Angeles', 'Chicago', 'Houston', 'Phoenix'],
    'Score': [85, 90, 78, 92, 88]
}
df_pivot = pd.DataFrame(data_pivot)
print(df_pivot)
Creating a pivot table:

python
Copy code
# Creating a pivot table
pivot_table = df_pivot.pivot_table(values='Score', index='City', columns='Age', aggfunc='mean')
print(pivot_table)
Creating a crosstab:

python
Copy code
# Creating a crosstab
crosstab = pd.crosstab(df_pivot['City'], df_pivot['Age'])
print(crosstab)
7.5 Melting and Stacking
Creating a DataFrame for melting and stacking:

python
Copy code
data_melt_stack = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Math': [85, 90, 78],
    'Science': [88, 92, 80]
}
df_melt_stack = pd.DataFrame(data_melt_stack)
print(df_melt_stack)
Melting a DataFrame:

python
Copy code
# Melting the DataFrame
df_melted = pd.melt(df_melt_stack, id_vars=['Name'], value_vars=['Math', 'Science'], var_name='Subject', value_name='Score')
print(df_melted)
Stacking a DataFrame:

python
Copy code
# Stacking the DataFrame
df_stacked = df_melt_stack.set_index('Name').stack()
print(df_stacked)
Unstacking a DataFrame:

python
Copy code
# Unstacking the DataFrame
df_unstacked = df_stacked.unstack()
print(df_unstacked)
By the end of this chapter, you should be proficient in transforming your data using sorting, merging, joining, concatenation, pivot tables, crosstabs, melting, and stacking. These skills are crucial for preparing and analyzing data effectively in Pandas.

