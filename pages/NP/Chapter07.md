# Universal Functions (ufuncs)
Universal functions, or ufuncs, are functions that operate element-wise on arrays in NumPy. They are essential for performing efficient and fast mathematical operations on arrays. This chapter will cover some commonly used ufuncs, including basic arithmetic functions and more advanced mathematical functions.

## Basic Arithmetic Functions
NumPy provides a variety of basic arithmetic ufuncs, which are optimized for performance and can handle broadcasting.

### np.add
The np.add function adds corresponding elements of two arrays.

```python
import numpy as np

# Creating two arrays
array1 = np.array([1, 2, 3, 4, 5])
array2 = np.array([10, 20, 30, 40, 50])

# Element-wise addition
result_add = np.add(array1, array2)
print("Addition:", result_add)
```

### np.subtract
The np.subtract function subtracts corresponding elements of one array from another.

```python
# Element-wise subtraction
result_subtract = np.subtract(array1, array2)
print("Subtraction:", result_subtract)
```

### np.multiply
The np.multiply function multiplies corresponding elements of two arrays.

```python
# Element-wise multiplication
result_multiply = np.multiply(array1, array2)
print("Multiplication:", result_multiply)
```

### np.divide
The np.divide function divides corresponding elements of one array by another.

```python
# Element-wise division
result_divide = np.divide(array1, array2)
print("Division:", result_divide)
```

## Power Function
### np.power
The np.power function raises elements of one array to the power of corresponding elements of another array.

```python
# Element-wise power
result_power = np.power(array1, 2)  # Squaring each element of array1
print("Power:", result_power)
```

## Trigonometric Functions
NumPy provides trigonometric functions that operate on angles given in radians.

### np.sin
The np.sin function computes the sine of each element in the array.

```python
# Creating an array of angles in radians
angles = np.array([0, np.pi / 2, np.pi])

# Sine of angles
result_sin = np.sin(angles)
print("Sine:", result_sin)
```

### np.cos
The np.cos function computes the cosine of each element in the array.

```python
# Cosine of angles
result_cos = np.cos(angles)
print("Cosine:", result_cos)
```

## Exponential and Logarithmic Functions
### np.exp
The np.exp function computes the exponential of each element in the array.

```python
# Creating an array
values = np.array([1, 2, 3])

# Exponential of values
result_exp = np.exp(values)
print("Exponential:", result_exp)
```

### np.log
The np.log function computes the natural logarithm (base e) of each element in the array.

```python
# Natural logarithm of values
result_log = np.log(values)
print("Natural Logarithm:", result_log)
```

## Example Code
Here are comprehensive examples demonstrating the use of various ufuncs:

```python
import numpy as np

# Creating arrays for arithmetic operations
array1 = np.array([1, 2, 3, 4, 5])
array2 = np.array([10, 20, 30, 40, 50])

# Basic arithmetic operations
result_add = np.add(array1, array2)
print("Addition:", result_add)

result_subtract = np.subtract(array1, array2)
print("Subtraction:", result_subtract)

result_multiply = np.multiply(array1, array2)
print("Multiplication:", result_multiply)

result_divide = np.divide(array1, array2)
print("Division:", result_divide)

# Power function
result_power = np.power(array1, 2)  # Squaring each element of array1
print("Power:", result_power)

# Trigonometric functions
angles = np.array([0, np.pi / 2, np.pi])
result_sin = np.sin(angles)
print("Sine:", result_sin)

result_cos = np.cos(angles)
print("Cosine:", result_cos)

# Exponential and logarithmic functions
values = np.array([1, 2, 3])
result_exp = np.exp(values)
print("Exponential:", result_exp)

result_log = np.log(values)
print("Natural Logarithm:", result_log)
```

## Summary
Universal functions (ufuncs) in NumPy provide efficient, element-wise operations for a wide range of mathematical computations. By using ufuncs, you can perform complex calculations with simple and readable code, leveraging the full power of NumPy for numerical computing.
