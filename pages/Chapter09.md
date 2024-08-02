# Chapter: Method Handling in Python
## Introduction
Methods in Python are functions that are associated with objects. They are used to perform operations on the data stored in an object. This chapter will cover the basics of method handling in Python, including defining methods, invoking methods, and using special methods. We'll provide examples to illustrate their usage and explain how methods enhance the functionality of Python classes.

## 1. Defining Methods
Methods are defined within a class using the def keyword. The first parameter of a method is always self, which refers to the instance of the class.

#### Example
```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def bark(self):
        return f"{self.name} says woof!"

# Creating an instance of the Dog class
dog = Dog("Buddy", 3)

# Calling the bark method
print(dog.bark())  # Output: Buddy says woof!
```

## 2. Instance Methods
Instance methods are the most common type of methods. They operate on instances of the class and can access and modify instance attributes.

### Example
```python
class Circle:
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14159 * self.radius ** 2

    def circumference(self):
        return 2 * 3.14159 * self.radius

#Creating an instance of the Circle class
circle = Circle(5)

#Calling instance methods
print("Area:", circle.area())  # Output: Area: 78.53975
print("Circumference:", circle.circumference())  # Output: Circumference: 31.4159
```

## 3. Class Methods
Class methods are methods that operate on the class itself rather than on instances of the class. They are defined using the @classmethod decorator and take cls as the first parameter, which refers to the class.

#### Example
```python
class Dog:
    species = "Canis familiaris"

    def __init__(self, name, age):
        self.name = name
        self.age = age

    @classmethod
    def get_species(cls):
        return cls.species

# Calling the class method
print(Dog.get_species())  # Output: Canis familiaris
```

## 4. Static Methods
Static methods are methods that do not operate on an instance or the class itself. They are defined using the @staticmethod decorator and do not take self or cls as parameters.

#### Example
```python
class MathOperations:
    @staticmethod
    def add(x, y):
        return x + y

    @staticmethod
    def multiply(x, y):
        return x * y

# Calling static methods
print("Sum:", MathOperations.add(5, 3))  # Output: Sum: 8
print("Product:", MathOperations.multiply(5, 3))  # Output: Product: 15
```

## 5. Special Methods
Special methods (also known as magic methods or dunder methods) are predefined methods in Python that begin and end with double underscores (__). These methods allow you to define how objects of a class behave with built-in Python operations.

### Example: __init__ Method
The __init__ method initializes an instance of the class.

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

# Creating an instance of the Person class
person = Person("Alice", 30)
print(person.name)  # Output: Alice
print(person.age)  # Output: 30
```

### Example: __str__ Method
The __str__ method defines the string representation of an object.

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def __str__(self):
        return f"Person(name={self.name}, age={self.age})"

# Creating an instance of the Person class
person = Person("Alice", 30)
print(person)  # Output: Person(name=Alice, age=30)
```

### Example: __len__ Method
The __len__ method returns the length of the object.

```python
class MyList:
    def __init__(self, items):
        self.items = items

    def __len__(self):
        return len(self.items)

# Creating an instance of the MyList class
my_list = MyList([1, 2, 3, 4])
print(len(my_list))  # Output: 4
```

## 6. Method Overriding
Method overriding allows a subclass to provide a specific implementation of a method that is already defined in its superclass.

#### Example
```python
class Animal:
    def make_sound(self):
        return "Some generic sound"

class Dog(Animal):
    def make_sound(self):
        return "Bark"

# Creating instances of the classes
generic_animal = Animal()
dog = Dog()

# Calling the make_sound method
print(generic_animal.make_sound())  # Output: Some generic sound
print(dog.make_sound())  # Output: Bark
```

## Examples and Applications
To better understand method handling, let's look at some practical examples.

### Example 1: Bank Account Class
```python
class BankAccount:
    def __init__(self, owner, balance=0):
        self.owner = owner
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount
        return self.balance

    def withdraw(self, amount):
        if amount > self.balance:
            return "Insufficient funds"
        else:
            self.balance -= amount
            return self.balance

# Creating an instance of the BankAccount class
account = BankAccount("John", 100)

# Performing operations
print(account.deposit(50))  # Output: 150
print(account.withdraw(30))  # Output: 120
print(account.withdraw(200))  # Output: Insufficient funds
```

## Example 2: Employee Class with Class Method
```python
class Employee:
    raise_amount = 1.05

    def __init__(self, first, last, salary):
        self.first = first
        self.last = last
        self.salary = salary

    def apply_raise(self):
        self.salary = int(self.salary * self.raise_amount)

    @classmethod
    def set_raise_amount(cls, amount):
        cls.raise_amount = amount

# Creating instances of the Employee class
emp1 = Employee("John", "Doe", 50000)
emp2 = Employee("Jane", "Smith", 60000)

# Applying raise and changing raise amount
emp1.apply_raise()
print(emp1.salary)  # Output: 52500

Employee.set_raise_amount(1.10)
emp2.apply_raise()
print(emp2.salary)  # Output: 66000
```

## Summary
In this chapter, we've explored method handling in Python. Methods are functions that are associated with objects and are used to perform operations on the data stored in an object. We've covered how to define and invoke instance methods, class methods, static methods, and special methods. We've also discussed method overriding and provided practical examples to illustrate the usage of methods. Understanding method handling is essential for writing object-oriented Python programs that are modular, maintainable, and reusable.


