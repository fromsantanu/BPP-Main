Concatenation and Splitting
NumPy provides several functions to concatenate and split arrays, enabling flexible manipulation of data structures. This chapter will cover concatenate, vstack, hstack for concatenation, and split, hsplit, vsplit for splitting arrays.

Concatenation
Concatenation refers to joining arrays along an existing axis.

np.concatenate
The np.concatenate function joins a sequence of arrays along an existing axis.

python
Copy code
import numpy as np

# Creating two 1D arrays
array1 = np.array([1, 2, 3])
array2 = np.array([4, 5, 6])

# Concatenating along the first axis
concatenated_array = np.concatenate((array1, array2))
print("Concatenated array:", concatenated_array)
np.vstack
The np.vstack function stacks arrays in sequence vertically (row-wise).

python
Copy code
# Creating two 2D arrays
array1 = np.array([[1, 2, 3], [4, 5, 6]])
array2 = np.array([[7, 8, 9], [10, 11, 12]])

# Vertical stacking
vstacked_array = np.vstack((array1, array2))
print("Vertically stacked array:\n", vstacked_array)
np.hstack
The np.hstack function stacks arrays in sequence horizontally (column-wise).

python
Copy code
# Horizontal stacking
hstacked_array = np.hstack((array1, array2))
print("Horizontally stacked array:\n", hstacked_array)
Splitting
Splitting breaks an array into multiple sub-arrays.

np.split
The np.split function splits an array into multiple sub-arrays along a specified axis.

python
Copy code
# Creating a 1D array
array = np.array([1, 2, 3, 4, 5, 6])

# Splitting into 3 sub-arrays
split_array = np.split(array, 3)
print("Split array:", split_array)
np.hsplit
The np.hsplit function splits an array into multiple sub-arrays horizontally (column-wise).

python
Copy code
# Creating a 2D array
array2d = np.array([[1, 2, 3, 4], [5, 6, 7, 8]])

# Horizontal split into 2 sub-arrays
hsplit_array = np.hsplit(array2d, 2)
print("Horizontally split array:")
for subarray in hsplit_array:
    print(subarray)
np.vsplit
The np.vsplit function splits an array into multiple sub-arrays vertically (row-wise).

python
Copy code
# Vertical split into 2 sub-arrays
vsplit_array = np.vsplit(array2d, 2)
print("Vertically split array:")
for subarray in vsplit_array:
    print(subarray)
Example Code
Here are comprehensive examples demonstrating concatenation and splitting:

Concatenation Examples
python
Copy code
import numpy as np

# Creating two 1D arrays
array1 = np.array([1, 2, 3])
array2 = np.array([4, 5, 6])

# Concatenating along the first axis
concatenated_array = np.concatenate((array1, array2))
print("Concatenated array:", concatenated_array)

# Creating two 2D arrays
array1_2d = np.array([[1, 2, 3], [4, 5, 6]])
array2_2d = np.array([[7, 8, 9], [10, 11, 12]])

# Vertical stacking
vstacked_array = np.vstack((array1_2d, array2_2d))
print("Vertically stacked array:\n", vstacked_array)

# Horizontal stacking
hstacked_array = np.hstack((array1_2d, array2_2d))
print("Horizontally stacked array:\n", hstacked_array)
Splitting Examples
python
Copy code
# Creating a 1D array
array = np.array([1, 2, 3, 4, 5, 6])

# Splitting into 3 sub-arrays
split_array = np.split(array, 3)
print("Split array:", split_array)

# Creating a 2D array
array2d = np.array([[1, 2, 3, 4], [5, 6, 7, 8]])

# Horizontal split into 2 sub-arrays
hsplit_array = np.hsplit(array2d, 2)
print("Horizontally split array:")
for subarray in hsplit_array:
    print(subarray)

# Vertical split into 2 sub-arrays
vsplit_array = np.vsplit(array2d, 2)
print("Vertically split array:")
for subarray in vsplit_array:
    print(subarray)
By understanding and utilizing these concatenation and splitting functions, you can efficiently manipulate and reorganize your data arrays to suit your needs. These operations are fundamental for data preprocessing and transformation in scientific and analytical computing.
