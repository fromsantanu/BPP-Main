# Basic Operations
NumPy provides a wide range of basic operations that can be performed on arrays. These operations are typically element-wise, making them very efficient for numerical computations.

## Element-wise Operations
Element-wise operations are operations that are applied to each element of the array individually. These operations include basic arithmetic operations like addition, subtraction, multiplication, and division.

### Creating Arrays
Before performing operations, let's create some example arrays:

```python
import numpy as np

# Creating two 1D arrays
array1 = np.array([1, 2, 3, 4, 5])
array2 = np.array([10, 20, 30, 40, 50])
```

## Basic Arithmetic Operations
### Addition
Element-wise addition adds the corresponding elements of two arrays.

```python
# Element-wise addition
addition_result = array1 + array2
print("Element-wise addition:", addition_result)
```

### Subtraction
Element-wise subtraction subtracts the corresponding elements of one array from another.

```python
# Element-wise subtraction
subtraction_result = array1 - array2
print("Element-wise subtraction:", subtraction_result)
```

### Multiplication
Element-wise multiplication multiplies the corresponding elements of two arrays.

```python
# Element-wise multiplication
multiplication_result = array1 * array2
print("Element-wise multiplication:", multiplication_result)
```

### Division
Element-wise division divides the corresponding elements of one array by another.

```python
# Element-wise division
division_result = array1 / array2
print("Element-wise division:", division_result)
```

## Example Code
Here are comprehensive examples demonstrating basic arithmetic operations with NumPy arrays:

```python
import numpy as np

# Creating two 1D arrays
array1 = np.array([1, 2, 3, 4, 5])
array2 = np.array([10, 20, 30, 40, 50])

# Element-wise addition
addition_result = array1 + array2
print("Element-wise addition:", addition_result)

# Element-wise subtraction
subtraction_result = array1 - array2
print("Element-wise subtraction:", subtraction_result)

# Element-wise multiplication
multiplication_result = array1 * array2
print("Element-wise multiplication:", multiplication_result)

# Element-wise division
division_result = array1 / array2
print("Element-wise division:", division_result)
```

## Broadcasting
NumPy also supports broadcasting, which allows arithmetic operations to be performed on arrays of different shapes. This is useful when you need to perform operations between arrays that are not the same size.

### Example of Broadcasting
```python
# Creating a 1D array and a scalar
array = np.array([1, 2, 3, 4, 5])
scalar = 10

# Broadcasting addition
broadcast_addition_result = array + scalar
print("Broadcasting addition:", broadcast_addition_result)

# Broadcasting subtraction
broadcast_subtraction_result = array - scalar
print("Broadcasting subtraction:", broadcast_subtraction_result)

# Broadcasting multiplication
broadcast_multiplication_result = array * scalar
print("Broadcasting multiplication:", broadcast_multiplication_result)

# Broadcasting division
broadcast_division_result = array / scalar
print("Broadcasting division:", broadcast_division_result)
```

By leveraging these basic operations and the power of broadcasting, you can perform a wide range of numerical computations efficiently with NumPy arrays. These operations form the foundation for more advanced numerical and scientific computations.
