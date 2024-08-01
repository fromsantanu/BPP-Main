# Chapter: Decision Structures in Python
## Introduction
Decision structures are essential in programming as they allow you to make decisions based on certain conditions. In Python, decision structures include if, if-else, and if-elif-else statements. These constructs enable the program to execute specific blocks of code based on the evaluation of conditions.

## 1. The if Statement
The if statement evaluates a condition. If the condition is true, the block of code within the if statement is executed.

#### Syntax
```python
if condition:
    # block of code
```

#### Example
```python
age = 18

if age >= 18:
    print("You are eligible to vote.")  # Output: You are eligible to vote.
```

## 2. The if-else Statement
The if-else statement provides an alternative block of code to execute when the if condition is false.

#### Syntax
```python
if condition:
    # block of code if condition is true
else:
    # block of code if condition is false
```

#### Example
```python
age = 16

if age >= 18:
    print("You are eligible to vote.")
else:
    print("You are not eligible to vote.")  # Output: You are not eligible to vote.
```

## 3. The if-elif-else Statement
The if-elif-else statement allows you to check multiple conditions. If the if condition is false, the elif (short for else if) conditions are checked in order. If none of the conditions are true, the else block is executed.

#### Syntax
```python
if condition1:
    # block of code if condition1 is true
elif condition2:
    # block of code if condition2 is true
elif condition3:
    # block of code if condition3 is true
else:
    # block of code if none of the conditions are true
```

#### Example
```python
marks = 85

if marks >= 90:
    print("Grade: A")
elif marks >= 80:
    print("Grade: B")  # Output: Grade: B
elif marks >= 70:
    print("Grade: C")
else:
    print("Grade: D")
```

## 4. Nested if Statements
You can use one if statement inside another if statement to create a nested decision structure.

#### Syntax
```python
if condition1:
    # block of code if condition1 is true
    if condition2:
        # block of code if condition2 is true
```

#### Example
```python
num = 10

if num > 0:
    print("The number is positive.")  # Output: The number is positive.
    if num % 2 == 0:
        print("The number is even.")  # Output: The number is even.
```

## 5. Using Logical Operators in Decision Structures
Logical operators like and, or, and not can be used to combine multiple conditions in a decision structure.

#### Example with and
```python
age = 25
is_student = True

if age < 30 and is_student:
    print("You are a young student.")  # Output: You are a young student.
```

#### Example with or
```python
age = 25
is_employed = False

if age < 30 or is_employed:
    print("You are either young or employed.")  # Output: You are either young or employed.
```

#### Example with not
```python
is_raining = False

if not is_raining:
    print("You can go outside.")  # Output: You can go outside.
```

## 6. Using Comparison Operators in Decision Structures
Comparison operators like ==, !=, <, >, <=, and >= are used to compare values in decision structures.

#### Example
```python
num1 = 10
num2 = 20

if num1 == num2:
    print("The numbers are equal.")
elif num1 != num2:
    print("The numbers are not equal.")  # Output: The numbers are not equal.

if num1 < num2:
    print("num1 is less than num2.")  # Output: num1 is less than num2.
elif num1 > num2:
    print("num1 is greater than num2.")
```

## Examples and Applications
To better understand decision structures, let's look at some practical examples.

### Example 1: Checking if a Number is Positive, Negative, or Zero
```python
num = -5

if num > 0:
    print("The number is positive.")
elif num < 0:
    print("The number is negative.")  # Output: The number is negative.
else:
    print("The number is zero.")
```

### Example 2: Categorizing Age Groups
```python
age = 45

if age < 18:
    print("You are a minor.")
elif age < 65:
    print("You are an adult.")  # Output: You are an adult.
else:
    print("You are a senior citizen.")
```

### Example 3: Calculating Discount Based on Purchase Amount
```python
purchase_amount = 150

if purchase_amount >= 100:
    discount = 0.2
elif purchase_amount >= 50:
    discount = 0.1
else:
    discount = 0.05

discount_amount = purchase_amount * discount
print("Discount amount:", discount_amount)  # Output: Discount amount: 30.0
```

## Summary
In this chapter, we've explored decision structures in Python, including if, if-else, and if-elif-else statements. We've also discussed nested if statements and how to use logical and comparison operators within decision structures. These constructs are essential for making decisions and controlling the flow of your program based on conditions. Mastering decision structures will enable you to write more dynamic and flexible Python programs.
