# Array Data Types and Attributes
NumPy arrays come with a variety of attributes that help you understand and manipulate the data they hold. This chapter will cover the key attributes and data types associated with NumPy arrays.

## Data Types (dtype)
The dtype attribute of a NumPy array indicates the data type of the elements stored in the array. NumPy supports many data types, including integers, floats, complex numbers, and more.

### Creating Arrays with Specific Data Types
```python
import numpy as np

# Integer array
int_array = np.array([1, 2, 3, 4, 5], dtype=np.int32)
print("Integer array:", int_array)
print("Data type:", int_array.dtype)

# Float array
float_array = np.array([1.1, 2.2, 3.3, 4.4, 5.5], dtype=np.float64)
print("Float array:", float_array)
print("Data type:", float_array.dtype)

# Complex array
complex_array = np.array([1 + 2j, 3 + 4j, 5 + 6j], dtype=np.complex128)
print("Complex array:", complex_array)
print("Data type:", complex_array.dtype)
```

### Shape, Size, and ndim
NumPy arrays have attributes that describe their structure:

- shape: The dimensions of the array.
- size: The total number of elements in the array.
- ndim: The number of dimensions (axes) of the array.

### Exploring Array Attributes
```python
# Creating a 2D array
array_2d = np.array([[1, 2, 3], [4, 5, 6]])

# Shape of the array
print("Shape of array:", array_2d.shape)

# Size of the array
print("Size of array:", array_2d.size)

# Number of dimensions
print("Number of dimensions:", array_2d.ndim)
```

### Itemsize and nbytes
NumPy arrays also have attributes that give information about the memory usage:

- itemsize: The size (in bytes) of each element in the array.
- nbytes: The total number of bytes consumed by the elements of the array.

### Memory Usage Attributes
```python
# Creating an array
array = np.array([1, 2, 3, 4, 5], dtype=np.int32)

# Size of each element in bytes
print("Item size:", array.itemsize, "bytes")

# Total number of bytes
print("Total bytes:", array.nbytes, "bytes")
```

## Code Examples
Here are comprehensive examples demonstrating the attributes of NumPy arrays:

### Example 1: Data Types (dtype)
```python
import numpy as np

# Integer array
int_array = np.array([1, 2, 3, 4, 5], dtype=np.int32)
print("Integer array:", int_array)
print("Data type:", int_array.dtype)

# Float array
float_array = np.array([1.1, 2.2, 3.3, 4.4, 5.5], dtype=np.float64)
print("Float array:", float_array)
print("Data type:", float_array.dtype)

# Complex array
complex_array = np.array([1 + 2j, 3 + 4j, 5 + 6j], dtype=np.complex128)
print("Complex array:", complex_array)
print("Data type:", complex_array.dtype)
```

### Example 2: Shape, Size, and ndim
```python
# Creating a 2D array
array_2d = np.array([[1, 2, 3], [4, 5, 6]])

# Shape of the array
print("Shape of array:", array_2d.shape)

# Size of the array
print("Size of array:", array_2d.size)

# Number of dimensions
print("Number of dimensions:", array_2d.ndim)
```

### Example 3: Itemsize and nbytes
```python
# Creating an array
array = np.array([1, 2, 3, 4, 5], dtype=np.int32)

# Size of each element in bytes
print("Item size:", array.itemsize, "bytes")

# Total number of bytes
print("Total bytes:", array.nbytes, "bytes")
```
By understanding these attributes, you can better manipulate and optimize the use of NumPy arrays in your data processing tasks.
