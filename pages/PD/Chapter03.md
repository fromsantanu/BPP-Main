Chapter 3: DataFrame
3.1 Creating a DataFrame
A DataFrame is a two-dimensional labeled data structure with columns of potentially different types. It is similar to a spreadsheet or a SQL table. You can create a DataFrame in several ways:

From a dictionary of lists:
python
Copy code
import pandas as pd

data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David'],
    'Age': [25, 30, 35, 40],
    'City': ['New York', 'Los Angeles', 'Chicago', 'Houston']
}
df = pd.DataFrame(data)
print(df)
From a list of dictionaries:
python
Copy code
data = [
    {'Name': 'Alice', 'Age': 25, 'City': 'New York'},
    {'Name': 'Bob', 'Age': 30, 'City': 'Los Angeles'},
    {'Name': 'Charlie', 'Age': 35, 'City': 'Chicago'},
    {'Name': 'David', 'Age': 40, 'City': 'Houston'}
]
df = pd.DataFrame(data)
print(df)
From a CSV file:
python
Copy code
df = pd.read_csv('data.csv')
print(df)
From a dictionary of Series:
python
Copy code
data = {
    'Name': pd.Series(['Alice', 'Bob', 'Charlie', 'David']),
    'Age': pd.Series([25, 30, 35, 40]),
    'City': pd.Series(['New York', 'Los Angeles', 'Chicago', 'Houston'])
}
df = pd.DataFrame(data)
print(df)
3.2 Accessing Data in a DataFrame
You can access data in a DataFrame using labels (column names) or integer location:

Accessing columns:
python
Copy code
print(df['Name'])
# Output:
# 0      Alice
# 1        Bob
# 2    Charlie
# 3      David
# Name: Name, dtype: object
Accessing rows:
Using iloc (integer-location based indexing):
python
Copy code
print(df.iloc[1])
# Output:
# Name             Bob
# Age               30
# City    Los Angeles
# Name: 1, dtype: object
Using loc (label-based indexing):
python
Copy code
print(df.loc[1])
# Output:
# Name             Bob
# Age               30
# City    Los Angeles
# Name: 1, dtype: object
Slicing rows and columns:
python
Copy code
print(df.iloc[1:3, 0:2])
# Output:
#       Name  Age
# 1      Bob   30
# 2  Charlie   35
Boolean indexing:
python
Copy code
print(df[df['Age'] > 30])
# Output:
#       Name  Age     City
# 2  Charlie   35  Chicago
# 3    David   40  Houston
3.3 DataFrame Operations
Pandas DataFrame supports various operations that facilitate data manipulation:

Arithmetic operations:
You can perform element-wise arithmetic operations on DataFrame columns:
python
Copy code
df['Age_plus_5'] = df['Age'] + 5
print(df)
# Output:
#       Name  Age         City  Age_plus_5
# 0    Alice   25     New York          30
# 1      Bob   30  Los Angeles          35
# 2  Charlie   35      Chicago          40
# 3    David   40      Houston          45
Statistical operations:
DataFrame provides a variety of statistical functions:
python
Copy code
print(df['Age'].mean())  # Output: 32.5
print(df['Age'].max())   # Output: 40
print(df['Age'].min())   # Output: 25
print(df['Age'].std())   # Output: 6.454972243679028
Applying functions:
You can apply custom functions to each element in a DataFrame using applymap, or to each column/row using apply:
python
Copy code
def add_ten(x):
    return x + 10

df['Age_plus_10'] = df['Age'].apply(add_ten)
print(df)
# Output:
#       Name  Age         City  Age_plus_5  Age_plus_10
# 0    Alice   25     New York          30           35
# 1      Bob   30  Los Angeles          35           40
# 2  Charlie   35      Chicago          40           45
# 3    David   40      Houston          45           50
Vectorized operations:
DataFrame operations are optimized for performance and are often vectorized:
python
Copy code
df['Age_multiplied'] = df['Age'] * 2
print(df)
# Output:
#       Name  Age         City  Age_plus_5  Age_plus_10  Age_multiplied
# 0    Alice   25     New York          30           35              50
# 1      Bob   30  Los Angeles          35           40              60
# 2  Charlie   35      Chicago          40           45              70
# 3    David   40      Houston          45           50              80
By the end of this chapter, you should be comfortable creating Pandas DataFrames, accessing their data, and performing various operations on them. These skills are crucial for more advanced data manipulation tasks in Pandas.
