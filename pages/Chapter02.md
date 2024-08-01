# Chapter: Fundamental and Collection Data Types in Python
## Introduction
Python is a versatile programming language with a rich set of data types that help in storing and manipulating data. These data types can be broadly categorized into fundamental data types and collection data types. This chapter will explore these categories, providing examples to illustrate their usage.

## 1. Fundamental Data Types
Fundamental data types are the basic building blocks in Python. These include numeric types, Boolean, and string types.

### Numeric Types
#### Integer (int): Represents whole numbers.

```python
age = 25
print(type(age))  # Output: <class 'int'>
```

### Float (float): Represents decimal numbers.

```python
height = 5.8
print(type(height))  # Output: <class 'float'>
```

### Complex (complex): Represents complex numbers with real and imaginary parts.

```python
complex_num = 3 + 4j
print(type(complex_num))  # Output: <class 'complex'>
```

### Boolean Type
Boolean (bool): Represents Boolean values True or False.

```python
is_student = True
print(type(is_student))  # Output: <class 'bool'>
```

### String Type
String (str): Represents a sequence of characters.

```python
name = "Alice"
print(type(name))  # Output: <class 'str'>
```

## 2. Collection Data Types
Collection data types are used to store collections of data. Python provides several built-in collection types, including lists, tuples, sets, and dictionaries.

### List
A list is an ordered collection of items. Lists are mutable, meaning their elements can be changed.

#### Creating a List

```python
fruits = ["apple", "banana", "cherry"]
print(fruits)  # Output: ['apple', 'banana', 'cherry']
```

#### Accessing List Elements

```python
print(fruits[0])  # Output: apple
```

#### Modifying List Elements

```python
fruits[1] = "blueberry"
print(fruits)  # Output: ['apple', 'blueberry', 'cherry']
```

#### Adding Elements to a List

```python
fruits.append("date")
print(fruits)  # Output: ['apple', 'blueberry', 'cherry', 'date']
```

#### Removing Elements from a List

```python
fruits.remove("blueberry")
print(fruits)  # Output: ['apple', 'cherry', 'date']
```

### Tuple
A tuple is an ordered collection of items that is immutable, meaning its elements cannot be changed.

#### Creating a Tuple

```python
colors = ("red", "green", "blue")
print(colors)  # Output: ('red', 'green', 'blue')
```

#### Accessing Tuple Elements

```python
print(colors[1])  # Output: green
```

### Tuples are Immutable

```python
# This will raise an error
# colors[1] = "yellow"
```
### Set
A set is an unordered collection of unique items.

#### Creating a Set

```python
unique_numbers = {1, 2, 3, 4, 5}
print(unique_numbers)  # Output: {1, 2, 3, 4, 5}
```

#### Adding Elements to a Set

```python
unique_numbers.add(6)
print(unique_numbers)  # Output: {1, 2, 3, 4, 5, 6}
```

#### Removing Elements from a Set

```python
unique_numbers.remove(4)
print(unique_numbers)  # Output: {1, 2, 3, 5, 6}
```

### Dictionary
A dictionary is an unordered collection of key-value pairs.

#### Creating a Dictionary

```python
person = {"name": "John", "age": 30}
print(person)  # Output: {'name': 'John', 'age': 30}
```

#### Accessing Dictionary Values

```python
print(person["name"])  # Output: John
```

#### Modifying Dictionary Values

```python
person["age"] = 31
print(person)  # Output: {'name': 'John', 'age': 31}
```

#### Adding Key-Value Pairs to a Dictionary

```python
person["city"] = "New York"
print(person)  # Output: {'name': 'John', 'age': 31, 'city': 'New York'}
```

Removing Key-Value Pairs from a Dictionary

```python
del person["age"]
print(person)  # Output: {'name': 'John', 'city': 'New York'}
```

## Examples and Applications
To better understand these data types, let's look at some practical examples.

### Example 1: Managing a Shopping List
```python
# Creating a shopping list
shopping_list = ["milk", "bread", "eggs"]

# Adding items to the list
shopping_list.append("butter")
shopping_list.append("jam")

# Removing an item from the list
shopping_list.remove("bread")

# Printing the final shopping list
print(shopping_list)  # Output: ['milk', 'eggs', 'butter', 'jam']
```

### Example 2: Storing Student Information
```python
# Creating a dictionary to store student information
student = {
    "name": "Alice",
    "age": 20,
    "courses": ["Math", "Physics"]
}

# Adding a new key-value pair
student["grade"] = "A"

# Modifying an existing value
student["age"] = 21

# Removing a key-value pair
del student["courses"]

# Printing the final student dictionary
print(student)  # Output: {'name': 'Alice', 'age': 21, 'grade': 'A'}
```

### Summary
In this chapter, we've explored the fundamental and collection data types in Python. Fundamental data types, including numeric, Boolean, and string types, form the basic building blocks of data in Python. Collection data types, such as lists, tuples, sets, and dictionaries, provide powerful ways to store and manage groups of related data. Understanding these data types is essential for writing efficient and effective Python programs, and mastering them will allow you to handle a wide variety of programming tasks with ease.

