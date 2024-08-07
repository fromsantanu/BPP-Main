Aggregations
Aggregations in NumPy allow you to summarize and derive key statistics from your data. This chapter covers some of the most commonly used aggregation functions: min, max, argmin, and argmax.

min
The min function returns the minimum value in the array or along a specified axis.

Example
python
Copy code
import numpy as np

# Creating an array
array = np.array([3, 1, 4, 1, 5, 9, 2, 6, 5])

# Minimum value in the array
min_value = np.min(array)
print("Minimum value:", min_value)

# Minimum value along an axis (2D array example)
array_2d = np.array([[1, 2, 3], [4, 0, 6], [7, 8, 9]])
min_axis0 = np.min(array_2d, axis=0)  # Min along columns
min_axis1 = np.min(array_2d, axis=1)  # Min along rows
print("Minimum along columns:", min_axis0)
print("Minimum along rows:", min_axis1)
max
The max function returns the maximum value in the array or along a specified axis.

Example
python
Copy code
# Maximum value in the array
max_value = np.max(array)
print("Maximum value:", max_value)

# Maximum value along an axis (2D array example)
max_axis0 = np.max(array_2d, axis=0)  # Max along columns
max_axis1 = np.max(array_2d, axis=1)  # Max along rows
print("Maximum along columns:", max_axis0)
print("Maximum along rows:", max_axis1)
argmin
The argmin function returns the indices of the minimum values in the array or along a specified axis.

Example
python
Copy code
# Index of the minimum value in the array
argmin_value = np.argmin(array)
print("Index of minimum value:", argmin_value)

# Index of the minimum value along an axis (2D array example)
argmin_axis0 = np.argmin(array_2d, axis=0)  # Index of min along columns
argmin_axis1 = np.argmin(array_2d, axis=1)  # Index of min along rows
print("Index of minimum along columns:", argmin_axis0)
print("Index of minimum along rows:", argmin_axis1)
argmax
The argmax function returns the indices of the maximum values in the array or along a specified axis.

Example
python
Copy code
# Index of the maximum value in the array
argmax_value = np.argmax(array)
print("Index of maximum value:", argmax_value)

# Index of the maximum value along an axis (2D array example)
argmax_axis0 = np.argmax(array_2d, axis=0)  # Index of max along columns
argmax_axis1 = np.argmax(array_2d, axis=1)  # Index of max along rows
print("Index of maximum along columns:", argmax_axis0)
print("Index of maximum along rows:", argmax_axis1)
Example Code
Here are comprehensive examples demonstrating the use of min, max, argmin, and argmax:

python
Copy code
import numpy as np

# Creating an array
array = np.array([3, 1, 4, 1, 5, 9, 2, 6, 5])

# Minimum value in the array
min_value = np.min(array)
print("Minimum value:", min_value)

# Creating a 2D array
array_2d = np.array([[1, 2, 3], [4, 0, 6], [7, 8, 9]])

# Minimum value along an axis
min_axis0 = np.min(array_2d, axis=0)  # Min along columns
min_axis1 = np.min(array_2d, axis=1)  # Min along rows
print("Minimum along columns:", min_axis0)
print("Minimum along rows:", min_axis1)

# Maximum value in the array
max_value = np.max(array)
print("Maximum value:", max_value)

# Maximum value along an axis
max_axis0 = np.max(array_2d, axis=0)  # Max along columns
max_axis1 = np.max(array_2d, axis=1)  # Max along rows
print("Maximum along columns:", max_axis0)
print("Maximum along rows:", max_axis1)

# Index of the minimum value in the array
argmin_value = np.argmin(array)
print("Index of minimum value:", argmin_value)

# Index of the minimum value along an axis
argmin_axis0 = np.argmin(array_2d, axis=0)  # Index of min along columns
argmin_axis1 = np.argmin(array_2d, axis=1)  # Index of min along rows
print("Index of minimum along columns:", argmin_axis0)
print("Index of minimum along rows:", argmin_axis1)

# Index of the maximum value in the array
argmax_value = np.argmax(array)
print("Index of maximum value:", argmax_value)

# Index of the maximum value along an axis
argmax_axis0 = np.argmax(array_2d, axis=0)  # Index of max along columns
argmax_axis1 = np.argmax(array_2d, axis=1)  # Index of max along rows
print("Index of maximum along columns:", argmax_axis0)
print("Index of maximum along rows:", argmax_axis1)
By using these aggregation functions, you can efficiently summarize and analyze your data arrays in NumPy, providing valuable insights into the distribution and characteristics of your data.
