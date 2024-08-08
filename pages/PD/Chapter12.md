# Chapter 12: Performance and Optimization
## 12.1 Memory Usage and Optimization
Understanding and optimizing memory usage can significantly improve the performance of your data processing tasks.

### Creating a sample DataFrame:

```python
import pandas as pd
import numpy as np

# Creating a large sample DataFrame
data = {
    'A': np.random.randint(0, 100, size=1000000),
    'B': np.random.rand(1000000),
    'C': np.random.choice(['X', 'Y', 'Z'], size=1000000)
}
df = pd.DataFrame(data)
print(df.info())
```

### Optimizing data types:

```python
# Optimizing integer columns
df['A'] = df['A'].astype('int8')

# Optimizing float columns
df['B'] = df['B'].astype('float32')

# Optimizing categorical columns
df['C'] = df['C'].astype('category')

print(df.info())
```

### Memory usage before and after optimization:

```python
# Memory usage before optimization
print("Memory usage before optimization:")
print(df.memory_usage(deep=True))

# Optimizing data types
df['A'] = df['A'].astype('int8')
df['B'] = df['B'].astype('float32')
df['C'] = df['C'].astype('category')

# Memory usage after optimization
print("Memory usage after optimization:")
print(df.memory_usage(deep=True))
```

## 12.2 Using eval and query for Performance
Pandas' eval and query methods allow for efficient operations on DataFrames by using a more optimized and faster backend.

### Creating a sample DataFrame:

```python
# Creating a sample DataFrame
data = {
    'A': np.random.randint(1, 100, size=100000),
    'B': np.random.randint(1, 100, size=100000),
    'C': np.random.randint(1, 100, size=100000),
    'D': np.random.randint(1, 100, size=100000)
}
df = pd.DataFrame(data)
print(df.head())
```

### Using eval for efficient calculations:

```python
# Performing arithmetic operations using eval
df['E'] = pd.eval('df.A + df.B - df.C * df.D / 2')
print(df.head())
```

### Comparing eval with traditional approach:

```python
# Traditional approach
df['E_traditional'] = df['A'] + df['B'] - df['C'] * df['D'] / 2

# Using eval
df['E_eval'] = pd.eval('df.A + df.B - df.C * df.D / 2')

print(df.head())
```

### Using query for efficient filtering:

```python
# Traditional approach
filtered_traditional = df[(df['A'] > 50) & (df['B'] < 50)]
print(filtered_traditional.head())

# Using query
filtered_query = df.query('A > 50 & B < 50')
print(filtered_query.head())
```

### Performance comparison:

```python
import time

# Timing traditional approach
start = time.time()
filtered_traditional = df[(df['A'] > 50) & (df['B'] < 50)]
end = time.time()
print(f"Traditional approach time: {end - start} seconds")

# Timing query approach
start = time.time()
filtered_query = df.query('A > 50 & B < 50')
end = time.time()
print(f"Query approach time: {end - start} seconds")
```

By the end of this chapter, you should be able to optimize the performance of your Pandas operations by reducing memory usage and utilizing the eval and query methods for efficient calculations and filtering. These skills are essential for handling large datasets and improving the speed of your data processing tasks.
