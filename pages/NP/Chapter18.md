Structured Arrays
Structured arrays in NumPy allow you to handle complex data types, similar to rows in a table or records in a database. Each element in a structured array can be a combination of multiple fields with different data types. This chapter covers the creation and manipulation of structured arrays using recarray and record.

Creating a Structured Array
You can create a structured array by defining a list of tuples that specify the name and data type of each field.

Example
python
Copy code
import numpy as np

# Defining the data type for the structured array
dtype = [('name', 'S10'), ('age', 'i4'), ('height', 'f4')]

# Creating the structured array
data = np.array([('Alice', 25, 5.5), ('Bob', 30, 5.9), ('Cathy', 28, 5.7)], dtype=dtype)

print("Structured Array:\n", data)
print("First record:", data[0])
print("Names:", data['name'])
print("Ages:", data['age'])
print("Heights:", data['height'])
Accessing and Modifying Structured Arrays
You can access and modify the fields in a structured array using field names.

Example
python
Copy code
# Accessing fields
names = data['name']
ages = data['age']
heights = data['height']

print("Names:", names)
print("Ages:", ages)
print("Heights:", heights)

# Modifying fields
data['age'] = [26, 31, 29]
print("Modified Ages:", data['age'])

data['height'][1] = 6.0
print("Modified Heights:\n", data)
Using recarray
The recarray is a subclass of ndarray that allows field access by attribute rather than only by index.

Example
python
Copy code
# Creating a recarray
rec_data = np.rec.array([('Alice', 25, 5.5), ('Bob', 30, 5.9), ('Cathy', 28, 5.7)], dtype=dtype)

print("Recarray:\n", rec_data)
print("First record:", rec_data[0])
print("Names:", rec_data.name)
print("Ages:", rec_data.age)
print("Heights:", rec_data.height)

# Modifying fields using attribute access
rec_data.age = [26, 31, 29]
print("Modified Ages:", rec_data.age)

rec_data.height[1] = 6.0
print("Modified Heights:\n", rec_data)
Using record Arrays
A record array allows attribute-style access to fields, but it is created using the np.core.records.fromarrays function.

Example
python
Copy code
# Creating a record array
record_data = np.core.records.fromarrays(
    [['Alice', 'Bob', 'Cathy'], [25, 30, 28], [5.5, 5.9, 5.7]],
    names='name, age, height'
)

print("Record Array:\n", record_data)
print("First record:", record_data[0])
print("Names:", record_data.name)
print("Ages:", record_data.age)
print("Heights:", record_data.height)

# Modifying fields using attribute access
record_data.age = [26, 31, 29]
print("Modified Ages:", record_data.age)

record_data.height[1] = 6.0
print("Modified Heights:\n", record_data)
Example Code
Here are comprehensive examples demonstrating the use of structured arrays, recarray, and record arrays:

python
Copy code
import numpy as np

# Defining the data type for the structured array
dtype = [('name', 'S10'), ('age', 'i4'), ('height', 'f4')]

# Creating the structured array
data = np.array([('Alice', 25, 5.5), ('Bob', 30, 5.9), ('Cathy', 28, 5.7)], dtype=dtype)
print("Structured Array:\n", data)
print("First record:", data[0])
print("Names:", data['name'])
print("Ages:", data['age'])
print("Heights:", data['height'])

# Accessing and modifying fields
data['age'] = [26, 31, 29]
print("Modified Ages:", data['age'])
data['height'][1] = 6.0
print("Modified Heights:\n", data)

# Creating a recarray
rec_data = np.rec.array([('Alice', 25, 5.5), ('Bob', 30, 5.9), ('Cathy', 28, 5.7)], dtype=dtype)
print("Recarray:\n", rec_data)
print("First record:", rec_data[0])
print("Names:", rec_data.name)
print("Ages:", rec_data.age)
print("Heights:", rec_data.height)

# Modifying fields using attribute access
rec_data.age = [26, 31, 29]
print("Modified Ages:", rec_data.age)
rec_data.height[1] = 6.0
print("Modified Heights:\n", rec_data)

# Creating a record array
record_data = np.core.records.fromarrays(
    [['Alice', 'Bob', 'Cathy'], [25, 30, 28], [5.5, 5.9, 5.7]],
    names='name, age, height'
)
print("Record Array:\n", record_data)
print("First record:", record_data[0])
print("Names:", record_data.name)
print("Ages:", record_data.age)
print("Heights:", record_data.height)

# Modifying fields using attribute access
record_data.age = [26, 31, 29]
print("Modified Ages:", record_data.age)
record_data.height[1] = 6.0
print("Modified Heights:\n", record_data)
By using structured arrays, recarray, and record arrays, you can efficiently manage and manipulate complex data structures in NumPy, enabling powerful data analysis and processing capabilities.
