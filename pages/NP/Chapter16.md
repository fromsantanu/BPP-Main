Reading and Writing Array Data
NumPy provides several functions for reading and writing array data to and from files. This chapter covers some of the most commonly used functions: loadtxt, savetxt, load, and save.

Reading and Writing Text Files
np.loadtxt
The loadtxt function reads data from a text file and loads it into an array. This function is useful for reading data that is structured in a tabular format (e.g., CSV files).

Example
python
Copy code
import numpy as np

# Creating a sample data file
np.savetxt("sample_data.txt", np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]]), delimiter=',')

# Loading data from a text file
loaded_data = np.loadtxt("sample_data.txt", delimiter=',')
print("Loaded data from text file:\n", loaded_data)
np.savetxt
The savetxt function writes array data to a text file. This function is useful for saving data in a human-readable format.

Example
python
Copy code
# Creating an array
array_to_save = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

# Saving array data to a text file
np.savetxt("saved_data.txt", array_to_save, delimiter=',')
print("Array data saved to saved_data.txt")
Reading and Writing Binary Files
np.load
The load function reads data from a binary file and loads it into an array. This function is useful for reading data that was previously saved using the save function.

Example
python
Copy code
# Saving array data to a binary file
np.save("binary_data.npy", array_to_save)
print("Array data saved to binary_data.npy")

# Loading data from a binary file
loaded_binary_data = np.load("binary_data.npy")
print("Loaded data from binary file:\n", loaded_binary_data)
np.save
The save function writes array data to a binary file. This function is useful for saving data in a format that can be efficiently read back into an array.

Example
python
Copy code
# Creating an array
array_to_save_binary = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

# Saving array data to a binary file
np.save("saved_binary_data.npy", array_to_save_binary)
print("Array data saved to saved_binary_data.npy")
Example Code
Here are comprehensive examples demonstrating the use of loadtxt, savetxt, load, and save:

Reading and Writing Text Files
python
Copy code
import numpy as np

# Creating an array
array_to_save_text = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

# Saving array data to a text file
np.savetxt("saved_text_data.txt", array_to_save_text, delimiter=',')
print("Array data saved to saved_text_data.txt")

# Loading data from a text file
loaded_text_data = np.loadtxt("saved_text_data.txt", delimiter=',')
print("Loaded data from text file:\n", loaded_text_data)
Reading and Writing Binary Files
python
Copy code
# Creating an array
array_to_save_binary = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

# Saving array data to a binary file
np.save("saved_binary_data.npy", array_to_save_binary)
print("Array data saved to saved_binary_data.npy")

# Loading data from a binary file
loaded_binary_data = np.load("saved_binary_data.npy")
print("Loaded data from binary file:\n", loaded_binary_data)
By using these functions, you can efficiently read and write array data to and from text and binary files, enabling the storage and retrieval of large datasets for analysis and processing in NumPy.
