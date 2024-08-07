NumPy in Machine Learning
NumPy is a fundamental tool in machine learning, providing essential functions for data manipulation and preparation. This chapter covers how to use NumPy for manipulating data and preparing datasets for machine learning algorithms.

Data Manipulation
Data manipulation is a crucial step in the machine learning pipeline. NumPy provides various functions to reshape, slice, index, and transform data.

Reshaping Arrays
Reshaping arrays is often necessary to match the input requirements of machine learning models.

Example: Reshaping Arrays
python
Copy code
import numpy as np

# Creating a 1D array
array_1d = np.array([1, 2, 3, 4, 5, 6])

# Reshaping to a 2D array
array_2d = array_1d.reshape((2, 3))
print("Reshaped to 2D array:\n", array_2d)

# Reshaping to a 3D array
array_3d = array_1d.reshape((2, 1, 3))
print("Reshaped to 3D array:\n", array_3d)
Slicing and Indexing
Slicing and indexing allow you to extract subsets of data, which is useful for creating training and test datasets.

Example: Slicing and Indexing
python
Copy code
# Creating a 2D array
array_2d = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

# Slicing to extract a subarray
subarray = array_2d[:2, 1:]
print("Sliced subarray:\n", subarray)

# Indexing to extract specific elements
indexed_elements = array_2d[[0, 2], [1, 2]]
print("Indexed elements:", indexed_elements)
Concatenating and Stacking Arrays
Concatenating and stacking arrays are common operations for combining multiple datasets.

Example: Concatenating and Stacking Arrays
python
Copy code
# Creating two 2D arrays
array1 = np.array([[1, 2], [3, 4]])
array2 = np.array([[5, 6], [7, 8]])

# Concatenating along the first axis
concatenated = np.concatenate((array1, array2), axis=0)
print("Concatenated along first axis:\n", concatenated)

# Stacking arrays vertically
vstacked = np.vstack((array1, array2))
print("Stacked vertically:\n", vstacked)

# Stacking arrays horizontally
hstacked = np.hstack((array1, array2))
print("Stacked horizontally:\n", hstacked)
Preparing Datasets for ML Algorithms
Preparing datasets involves cleaning, normalizing, splitting, and encoding data to be suitable for machine learning algorithms.

Normalizing Data
Normalization scales data to a specific range, typically [0, 1], ensuring that all features contribute equally to the analysis.

Example: Normalizing Data
python
Copy code
# Creating an array
data = np.array([[1, 2], [3, 4], [5, 6]])

# Normalizing the data to the range [0, 1]
normalized_data = (data - np.min(data)) / (np.max(data) - np.min(data))
print("Normalized data:\n", normalized_data)
Standardizing Data
Standardization scales data to have a mean of 0 and a standard deviation of 1.

Example: Standardizing Data
python
Copy code
# Standardizing the data
mean = np.mean(data, axis=0)
std = np.std(data, axis=0)
standardized_data = (data - mean) / std
print("Standardized data:\n", standardized_data)
Splitting Datasets
Splitting datasets into training and test sets is essential for evaluating machine learning models.

Example: Splitting Datasets
python
Copy code
# Creating a dataset
data = np.array([[1, 2], [3, 4], [5, 6], [7, 8]])
labels = np.array([0, 1, 0, 1])

# Splitting into training and test sets
train_data = data[:3]
test_data = data[3:]
train_labels = labels[:3]
test_labels = labels[3:]

print("Training data:\n", train_data)
print("Test data:\n", test_data)
print("Training labels:", train_labels)
print("Test labels:", test_labels)
Encoding Categorical Data
Encoding categorical data is necessary for many machine learning algorithms, which require numerical input.

Example: Encoding Categorical Data
python
Copy code
from sklearn.preprocessing import OneHotEncoder

# Creating categorical data
categorical_data = np.array([['red'], ['blue'], ['green'], ['blue']])

# Encoding categorical data
encoder = OneHotEncoder(sparse=False)
encoded_data = encoder.fit_transform(categorical_data)
print("Encoded data:\n", encoded_data)
Example Code
Here are comprehensive examples demonstrating data manipulation and preparation for machine learning:

python
Copy code
import numpy as np
from sklearn.preprocessing import OneHotEncoder

# Data Manipulation
array_1d = np.array([1, 2, 3, 4, 5, 6])
array_2d = array_1d.reshape((2, 3))
print("Reshaped to 2D array:\n", array_2d)

array_3d = array_1d.reshape((2, 1, 3))
print("Reshaped to 3D array:\n", array_3d)

array_2d = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
subarray = array_2d[:2, 1:]
print("Sliced subarray:\n", subarray)

indexed_elements = array_2d[[0, 2], [1, 2]]
print("Indexed elements:", indexed_elements)

array1 = np.array([[1, 2], [3, 4]])
array2 = np.array([[5, 6], [7, 8]])
concatenated = np.concatenate((array1, array2), axis=0)
print("Concatenated along first axis:\n", concatenated)

vstacked = np.vstack((array1, array2))
print("Stacked vertically:\n", vstacked)

hstacked = np.hstack((array1, array2))
print("Stacked horizontally:\n", hstacked)

# Preparing Datasets for ML Algorithms
data = np.array([[1, 2], [3, 4], [5, 6]])
normalized_data = (data - np.min(data)) / (np.max(data) - np.min(data))
print("Normalized data:\n", normalized_data)

mean = np.mean(data, axis=0)
std = np.std(data, axis=0)
standardized_data = (data - mean) / std
print("Standardized data:\n", standardized_data)

data = np.array([[1, 2], [3, 4], [5, 6], [7, 8]])
labels = np.array([0, 1, 0, 1])
train_data = data[:3]
test_data = data[3:]
train_labels = labels[:3]
test_labels = labels[3:]
print("Training data:\n", train_data)
print("Test data:\n", test_data)
print("Training labels:", train_labels)
print("Test labels:", test_labels)

categorical_data = np.array([['red'], ['blue'], ['green'], ['blue']])
encoder = OneHotEncoder(sparse=False)
encoded_data = encoder.fit_transform(categorical_data)
print("Encoded data:\n", encoded_data)
By leveraging these techniques, you can effectively manipulate data and prepare datasets for machine learning algorithms using NumPy, enabling efficient and scalable machine learning workflows.
