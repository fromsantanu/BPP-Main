# Array Transposition
Transposing arrays is a common operation in NumPy that involves flipping an array over its diagonal, switching its rows with columns. This chapter covers three methods for transposing arrays: transpose, swapaxes, and the .T attribute.

## Transpose
The transpose function in NumPy allows you to permute the dimensions of an array.

### Example 1: Transposing a 2D Array
```python
import numpy as np

# Creating a 2D array
array_2d = np.array([[1, 2, 3], [4, 5, 6]])

# Transposing the array
transposed_array = np.transpose(array_2d)
print("Original array:\n", array_2d)
print("Transposed array:\n", transposed_array)
```

### Example 2: Transposing a 3D Array
```python
# Creating a 3D array
array_3d = np.array([[[1, 2, 3], [4, 5, 6]], [[7, 8, 9], [10, 11, 12]]])

# Transposing the array (swap axes 0 and 1)
transposed_array_3d = np.transpose(array_3d, (1, 0, 2))
print("Original 3D array:\n", array_3d)
print("Transposed 3D array:\n", transposed_array_3d)
```

## Swapaxes
The swapaxes function allows you to swap two specified axes of an array.

### Example
```python
# Creating a 3D array
array_3d = np.array([[[1, 2, 3], [4, 5, 6]], [[7, 8, 9], [10, 11, 12]]])

# Swapping axes 0 and 2
swapped_axes_array = np.swapaxes(array_3d, 0, 2)
print("Original 3D array:\n", array_3d)
print("Array after swapping axes 0 and 2:\n", swapped_axes_array)
```

## T Attribute
The .T attribute is a shorthand for transposing a 2D array. It is equivalent to calling the transpose method.

### Example
```python
# Creating a 2D array
array_2d = np.array([[1, 2, 3], [4, 5, 6]])

# Transposing the array using .T
transposed_array_T = array_2d.T
print("Original array:\n", array_2d)
print("Transposed array using .T:\n", transposed_array_T)
```

## Example Code
Here are comprehensive examples demonstrating the use of transpose, swapaxes, and .T:

### Transpose Examples
```python
import numpy as np

# Creating a 2D array
array_2d = np.array([[1, 2, 3], [4, 5, 6]])

# Transposing the array
transposed_array = np.transpose(array_2d)
print("Original array:\n", array_2d)
print("Transposed array:\n", transposed_array)

# Creating a 3D array
array_3d = np.array([[[1, 2, 3], [4, 5, 6]], [[7, 8, 9], [10, 11, 12]]])

# Transposing the array (swap axes 0 and 1)
transposed_array_3d = np.transpose(array_3d, (1, 0, 2))
print("Original 3D array:\n", array_3d)
print("Transposed 3D array:\n", transposed_array_3d)
```

### Swapaxes Example
```python
# Creating a 3D array
array_3d = np.array([[[1, 2, 3], [4, 5, 6]], [[7, 8, 9], [10, 11, 12]]])

# Swapping axes 0 and 2
swapped_axes_array = np.swapaxes(array_3d, 0, 2)
print("Original 3D array:\n", array_3d)
print("Array after swapping axes 0 and 2:\n", swapped_axes_array)
```

### T Attribute Example
```python
# Creating a 2D array
array_2d = np.array([[1, 2, 3], [4, 5, 6]])

# Transposing the array using .T
transposed_array_T = array_2d.T
print("Original array:\n", array_2d)
print("Transposed array using .T:\n", transposed_array_T)
```

By mastering these transposition techniques, you can efficiently manipulate and analyze your data arrays in NumPy, making your data processing tasks more effective and flexible.
