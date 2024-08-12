# Memory Layout and Views
Understanding the memory layout of arrays and how to create views is essential for efficient data manipulation in NumPy. This chapter covers the base attribute, ascontiguousarray, and asfortranarray.

## base Attribute
The base attribute of a NumPy array indicates the base object if the array is a view. If the array owns its data, base is None.

### Example
```python
import numpy as np

# Creating an array
original_array = np.array([1, 2, 3, 4, 5])

# Creating a view of the array
view_array = original_array[1:4]

# Checking the base attribute
print("Original array:", original_array)
print("View array:", view_array)
print("Base of view array:", view_array.base)

# Creating a copy of the array
copy_array = original_array.copy()

# Checking the base attribute
print("Copy array:", copy_array)
print("Base of copy array:", copy_array.base)
```

## ascontiguousarray
The ascontiguousarray function returns a contiguous array in memory (C order). This is useful when you need to ensure that an array is stored in a contiguous block of memory.

### Example
```python
# Creating a Fortran-order array (column-major order)
fortran_array = np.asfortranarray(np.array([[1, 2, 3], [4, 5, 6]]))
print("Fortran-order array:\n", fortran_array)

# Converting to a contiguous array (C order)
contiguous_array = np.ascontiguousarray(fortran_array)
print("Contiguous array (C order):\n", contiguous_array)

# Checking the memory layout
print("Fortran array is C contiguous:", fortran_array.flags['C_CONTIGUOUS'])
print("Contiguous array is C contiguous:", contiguous_array.flags['C_CONTIGUOUS'])
```

## asfortranarray
The asfortranarray function returns an array in Fortran order (column-major order). This is useful for interfacing with Fortran libraries or when column-major order is desired.

### Example
```python
# Creating a C-order array (row-major order)
c_order_array = np.array([[1, 2, 3], [4, 5, 6]])
print("C-order array:\n", c_order_array)

# Converting to a Fortran-order array
fortran_array = np.asfortranarray(c_order_array)
print("Fortran-order array (column-major order):\n", fortran_array)

# Checking the memory layout
print("C-order array is Fortran contiguous:", c_order_array.flags['F_CONTIGUOUS'])
print("Fortran array is Fortran contiguous:", fortran_array.flags['F_CONTIGUOUS'])
```

## Example Code
Here are comprehensive examples demonstrating the use of the base attribute, ascontiguousarray, and asfortranarray:

```python
import numpy as np

# Base attribute example
original_array = np.array([1, 2, 3, 4, 5])
view_array = original_array[1:4]

print("Original array:", original_array)
print("View array:", view_array)
print("Base of view array:", view_array.base)

copy_array = original_array.copy()
print("Copy array:", copy_array)
print("Base of copy array:", copy_array.base)

# ascontiguousarray example
fortran_array = np.asfortranarray(np.array([[1, 2, 3], [4, 5, 6]]))
print("Fortran-order array:\n", fortran_array)

contiguous_array = np.ascontiguousarray(fortran_array)
print("Contiguous array (C order):\n", contiguous_array)

print("Fortran array is C contiguous:", fortran_array.flags['C_CONTIGUOUS'])
print("Contiguous array is C contiguous:", contiguous_array.flags['C_CONTIGUOUS'])

# asfortranarray example
c_order_array = np.array([[1, 2, 3], [4, 5, 6]])
print("C-order array:\n", c_order_array)

fortran_array = np.asfortranarray(c_order_array)
print("Fortran-order array (column-major order):\n", fortran_array)

print("C-order array is Fortran contiguous:", c_order_array.flags['F_CONTIGUOUS'])
print("Fortran array is Fortran contiguous:", fortran_array.flags['F_CONTIGUOUS'])
```

By understanding and utilizing these memory layout functions and attributes, you can ensure efficient memory usage and data manipulation in NumPy, which is crucial for high-performance computing and data analysis.

