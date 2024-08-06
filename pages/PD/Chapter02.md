# Chapter 2: Series
## 2.1 Creating a Series
A Series is a one-dimensional labeled array capable of holding any data type (integers, strings, floating point numbers, Python objects, etc.). It is similar to a column in a spreadsheet or a database table. You can create a Series in several ways:

### From a list:
```python
import pandas as pd

data = [10, 20, 30, 40]
series_from_list = pd.Series(data)
print(series_from_list)
```

### From a dictionary:
```python
data = {'a': 10, 'b': 20, 'c': 30, 'd': 40}
series_from_dict = pd.Series(data)
print(series_from_dict)
```

### From a scalar value:
```python
series_from_scalar = pd.Series(5, index=['a', 'b', 'c', 'd'])
print(series_from_scalar)
```

## 2.2 Accessing Data in a Series
You can access data in a Series using labels (index) or integer location:

### Using labels:
```python
print(series_from_dict['b'])  # Output: 20
```

### Using integer location:
```python
print(series_from_list[1])  # Output: 20
```

### Slicing:
```python
print(series_from_list[1:3])

# Output:
# 1    20
# 2    30
# dtype: int64
```

### Boolean indexing:
```python
print(series_from_list[series_from_list > 20])

# Output:
# 2    30
# 3    40
# dtype: int64
```

## 2.3 Series Operations
Pandas Series supports various operations that make data manipulation easy and efficient:

### Arithmetic operations:
You can perform element-wise arithmetic operations on Series:

```python
series1 = pd.Series([1, 2, 3, 4])
series2 = pd.Series([10, 20, 30, 40])

sum_series = series1 + series2
print(sum_series)

# Output:
# 0    11
# 1    22
# 2    33
# 3    44
# dtype: int64
```

### Statistical operations:
Series provides a variety of statistical functions:
```python
print(series1.mean())  # Output: 2.5
print(series1.max())   # Output: 4
print(series1.min())   # Output: 1
print(series1.std())   # Output: 1.2909944487358056
```

### Applying functions:
You can apply custom functions to each element in the Series using apply:

```python
def square(x):
    return x * x

squared_series = series1.apply(square)
print(squared_series)

# Output:
# 0     1
# 1     4
# 2     9
# 3    16
# dtype: int64
```

### Vectorized operations:
Series operations are optimized for performance and are often vectorized:
```python
series3 = pd.Series([2, 4, 6, 8])
print(series3 + 5)

# Output:
# 0     7
# 1     9
# 2    11
# 3    13
# dtype: int64
```

By the end of this chapter, you should be comfortable creating Pandas Series, accessing their data, and performing various operations on them. These skills form the foundation for more complex data manipulation tasks in Pandas.
