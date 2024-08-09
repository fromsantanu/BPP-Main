# Basic Statistics
NumPy provides a variety of functions to perform basic statistical operations on arrays. This chapter covers some of the most commonly used statistical functions: sum, mean, median, std, and var.

## Sum
The sum function calculates the sum of all elements in the array or along a specified axis.

### Example
```python
import numpy as np

# Creating an array
array = np.array([1, 2, 3, 4, 5])

# Sum of all elements
total_sum = np.sum(array)
print("Sum of all elements:", total_sum)

# Sum along axis (2D array example)
array_2d = np.array([[1, 2, 3], [4, 5, 6]])
sum_axis0 = np.sum(array_2d, axis=0)  # Sum along columns
sum_axis1 = np.sum(array_2d, axis=1)  # Sum along rows
print("Sum along columns:", sum_axis0)
print("Sum along rows:", sum_axis1)
```

## Mean
The mean function calculates the arithmetic mean of all elements in the array or along a specified axis.

### Example
```python
# Mean of all elements
mean_value = np.mean(array)
print("Mean of all elements:", mean_value)

# Mean along axis (2D array example)
mean_axis0 = np.mean(array_2d, axis=0)  # Mean along columns
mean_axis1 = np.mean(array_2d, axis=1)  # Mean along rows
print("Mean along columns:", mean_axis0)
print("Mean along rows:", mean_axis1)
```

## Median
The median function calculates the median of all elements in the array or along a specified axis.

### Example
```python
# Median of all elements
median_value = np.median(array)
print("Median of all elements:", median_value)

# Median along axis (2D array example)
median_axis0 = np.median(array_2d, axis=0)  # Median along columns
median_axis1 = np.median(array_2d, axis=1)  # Median along rows
print("Median along columns:", median_axis0)
print("Median along rows:", median_axis1)
```

## Standard Deviation
The std function calculates the standard deviation of all elements in the array or along a specified axis.

### Example
```python
# Standard deviation of all elements
std_value = np.std(array)
print("Standard deviation of all elements:", std_value)

# Standard deviation along axis (2D array example)
std_axis0 = np.std(array_2d, axis=0)  # Std along columns
std_axis1 = np.std(array_2d, axis=1)  # Std along rows
print("Standard deviation along columns:", std_axis0)
print("Standard deviation along rows:", std_axis1)
```

## Variance
The var function calculates the variance of all elements in the array or along a specified axis.

### Example
```python
# Variance of all elements
var_value = np.var(array)
print("Variance of all elements:", var_value)

# Variance along axis (2D array example)
var_axis0 = np.var(array_2d, axis=0)  # Variance along columns
var_axis1 = np.var(array_2d, axis=1)  # Variance along rows
print("Variance along columns:", var_axis0)
print("Variance along rows:", var_axis1)

## Example Code
Here are comprehensive examples demonstrating the use of sum, mean, median, std, and var:

```python
import numpy as np

# Creating an array
array = np.array([1, 2, 3, 4, 5])

# Sum of all elements
total_sum = np.sum(array)
print("Sum of all elements:", total_sum)

# Creating a 2D array
array_2d = np.array([[1, 2, 3], [4, 5, 6]])

# Sum along axis
sum_axis0 = np.sum(array_2d, axis=0)  # Sum along columns
sum_axis1 = np.sum(array_2d, axis=1)  # Sum along rows
print("Sum along columns:", sum_axis0)
print("Sum along rows:", sum_axis1)

# Mean of all elements
mean_value = np.mean(array)
print("Mean of all elements:", mean_value)

# Mean along axis
mean_axis0 = np.mean(array_2d, axis=0)  # Mean along columns
mean_axis1 = np.mean(array_2d, axis=1)  # Mean along rows
print("Mean along columns:", mean_axis0)
print("Mean along rows:", mean_axis1)

# Median of all elements
median_value = np.median(array)
print("Median of all elements:", median_value)

# Median along axis
median_axis0 = np.median(array_2d, axis=0)  # Median along columns
median_axis1 = np.median(array_2d, axis=1)  # Median along rows
print("Median along columns:", median_axis0)
print("Median along rows:", median_axis1)

# Standard deviation of all elements
std_value = np.std(array)
print("Standard deviation of all elements:", std_value)

# Standard deviation along axis
std_axis0 = np.std(array_2d, axis=0)  # Std along columns
std_axis1 = np.std(array_2d, axis=1)  # Std along rows
print("Standard deviation along columns:", std_axis0)
print("Standard deviation along rows:", std_axis1)

# Variance of all elements
var_value = np.var(array)
print("Variance of all elements:", var_value)

# Variance along axis
var_axis0 = np.var(array_2d, axis=0)  # Variance along columns
var_axis1 = np.var(array_2d, axis=1)  # Variance along rows
print("Variance along columns:", var_axis0)
print("Variance along rows:", var_axis1)
```

By using these basic statistical functions, you can easily perform essential statistical analysis on your data arrays in NumPy, making your data processing tasks more efficient and insightful.

