# Array Indexing and Slicing
NumPy arrays provide powerful tools for accessing and modifying their elements. This chapter will cover basic slicing and indexing, boolean indexing, and fancy indexing with examples.

## Basic Slicing and Indexing
Basic slicing and indexing in NumPy arrays are similar to Python lists but more powerful. You can use indices to access and modify individual elements or slices (subarrays) of an array.

### Accessing Elements
```python
import numpy as np

# Creating a 1D array
array_1d = np.array([10, 20, 30, 40, 50])

# Accessing individual elements
print("First element:", array_1d[0])
print("Last element:", array_1d[-1])
```

### Slicing Arrays
Slicing allows you to extract subarrays using the colon : operator.

```python
# Slicing a 1D array
print("First three elements:", array_1d[:3])
print("Last two elements:", array_1d[-2:])

# Creating a 2D array
array_2d = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

# Slicing rows
print("First row:", array_2d[0, :])
print("Second and third rows:", array_2d[1:, :])

# Slicing columns
print("First column:", array_2d[:, 0])
print("Second and third columns:", array_2d[:, 1:])
```

### Boolean Indexing
Boolean indexing allows you to select elements from an array that satisfy certain conditions. This is useful for filtering data.

```python
# Creating an array
array = np.array([10, 20, 30, 40, 50])

# Boolean indexing
bool_index = array > 30
print("Boolean index:", bool_index)

# Applying boolean index
filtered_array = array[bool_index]
print("Filtered array:", filtered_array)
```

### Fancy Indexing
Fancy indexing allows you to access multiple array elements at once using lists or arrays of indices.

```python
# Creating a 1D array
array = np.array([10, 20, 30, 40, 50])

# Fancy indexing with a list of indices
indices = [0, 2, 4]
fancy_indexed_array = array[indices]
print("Fancy indexed array:", fancy_indexed_array)

# Creating a 2D array
array_2d = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

# Fancy indexing rows and columns
row_indices = [0, 2]
col_indices = [1, 2]
fancy_indexed_2d = array_2d[row_indices, :]
print("Fancy indexed rows:\n", fancy_indexed_2d)

fancy_indexed_2d_cols = array_2d[:, col_indices]
print("Fancy indexed columns:\n", fancy_indexed_2d_cols)
```

## Code Examples
Here are comprehensive examples demonstrating array indexing and slicing:

### Example 1: Basic Slicing and Indexing
```python
import numpy as np

# Creating a 1D array
array_1d = np.array([10, 20, 30, 40, 50])

# Accessing individual elements
print("First element:", array_1d[0])
print("Last element:", array_1d[-1])

# Slicing a 1D array
print("First three elements:", array_1d[:3])
print("Last two elements:", array_1d[-2:])

# Creating a 2D array
array_2d = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

# Slicing rows
print("First row:", array_2d[0, :])
print("Second and third rows:", array_2d[1:, :])

# Slicing columns
print("First column:", array_2d[:, 0])
print("Second and third columns:", array_2d[:, 1:])
```

### Example 2: Boolean Indexing
```python
# Creating an array
array = np.array([10, 20, 30, 40, 50])

# Boolean indexing
bool_index = array > 30
print("Boolean index:", bool_index)

# Applying boolean index
filtered_array = array[bool_index]
print("Filtered array:", filtered_array)
```

### Example 3: Fancy Indexing
```python
# Creating a 1D array
array = np.array([10, 20, 30, 40, 50])

# Fancy indexing with a list of indices
indices = [0, 2, 4]
fancy_indexed_array = array[indices]
print("Fancy indexed array:", fancy_indexed_array)

# Creating a 2D array
array_2d = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

# Fancy indexing rows and columns
row_indices = [0, 2]
col_indices = [1, 2]
fancy_indexed_2d = array_2d[row_indices, :]
print("Fancy indexed rows:\n", fancy_indexed_2d)

fancy_indexed_2d_cols = array_2d[:, col_indices]
print("Fancy indexed columns:\n", fancy_indexed_2d_cols)
```

By mastering these indexing and slicing techniques, you can efficiently access and manipulate data within NumPy arrays, making your data processing tasks more effective and efficient.
