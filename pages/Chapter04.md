Chapter: Decision Structures in Python
Introduction
Decision structures are essential in programming as they allow you to make decisions based on certain conditions. In Python, decision structures include if, if-else, and if-elif-else statements. These constructs enable the program to execute specific blocks of code based on the evaluation of conditions.

1. The if Statement
The if statement evaluates a condition. If the condition is true, the block of code within the if statement is executed.

Syntax
python
Copy code
if condition:
    # block of code
Example
python
Copy code
age = 18

if age >= 18:
    print("You are eligible to vote.")  # Output: You are eligible to vote.
2. The if-else Statement
The if-else statement provides an alternative block of code to execute when the if condition is false.

Syntax
python
Copy code
if condition:
    # block of code if condition is true
else:
    # block of code if condition is false
Example
python
Copy code
age = 16

if age >= 18:
    print("You are eligible to vote.")
else:
    print("You are not eligible to vote.")  # Output: You are not eligible to vote.
3. The if-elif-else Statement
The if-elif-else statement allows you to check multiple conditions. If the if condition is false, the elif (short for else if) conditions are checked in order. If none of the conditions are true, the else block is executed.

Syntax
python
Copy code
if condition1:
    # block of code if condition1 is true
elif condition2:
    # block of code if condition2 is true
elif condition3:
    # block of code if condition3 is true
else:
    # block of code if none of the conditions are true
Example
python
Copy code
marks = 85

if marks >= 90:
    print("Grade: A")
elif marks >= 80:
    print("Grade: B")  # Output: Grade: B
elif marks >= 70:
    print("Grade: C")
else:
    print("Grade: D")
4. Nested if Statements
You can use one if statement inside another if statement to create a nested decision structure.

Syntax
python
Copy code
if condition1:
    # block of code if condition1 is true
    if condition2:
        # block of code if condition2 is true
Example
python
Copy code
num = 10

if num > 0:
    print("The number is positive.")  # Output: The number is positive.
    if num % 2 == 0:
        print("The number is even.")  # Output: The number is even.
5. Using Logical Operators in Decision Structures
Logical operators like and, or, and not can be used to combine multiple conditions in a decision structure.

Example with and
python
Copy code
age = 25
is_student = True

if age < 30 and is_student:
    print("You are a young student.")  # Output: You are a young student.
Example with or
python
Copy code
age = 25
is_employed = False

if age < 30 or is_employed:
    print("You are either young or employed.")  # Output: You are either young or employed.
Example with not
python
Copy code
is_raining = False

if not is_raining:
    print("You can go outside.")  # Output: You can go outside.
6. Using Comparison Operators in Decision Structures
Comparison operators like ==, !=, <, >, <=, and >= are used to compare values in decision structures.

Example
python
Copy code
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
Examples and Applications
To better understand decision structures, let's look at some practical examples.

Example 1: Checking if a Number is Positive, Negative, or Zero
python
Copy code
num = -5

if num > 0:
    print("The number is positive.")
elif num < 0:
    print("The number is negative.")  # Output: The number is negative.
else:
    print("The number is zero.")
Example 2: Categorizing Age Groups
python
Copy code
age = 45

if age < 18:
    print("You are a minor.")
elif age < 65:
    print("You are an adult.")  # Output: You are an adult.
else:
    print("You are a senior citizen.")
Example 3: Calculating Discount Based on Purchase Amount
python
Copy code
purchase_amount = 150

if purchase_amount >= 100:
    discount = 0.2
elif purchase_amount >= 50:
    discount = 0.1
else:
    discount = 0.05

discount_amount = purchase_amount * discount
print("Discount amount:", discount_amount)  # Output: Discount amount: 30.0
Summary
In this chapter, we've explored decision structures in Python, including if, if-else, and if-elif-else statements. We've also discussed nested if statements and how to use logical and comparison operators within decision structures. These constructs are essential for making decisions and controlling the flow of your program based on conditions. Mastering decision structures will enable you to write more dynamic and flexible Python programs.


Please generate a chapter on the topic "Repetitive Structures" in Python with examples.
ChatGPT
Chapter: Repetitive Structures in Python
Introduction
Repetitive structures, also known as loops, are fundamental in programming as they allow you to execute a block of code multiple times. In Python, the primary looping structures are for and while loops. This chapter will explore these loops, providing examples to illustrate their usage.

1. The for Loop
The for loop in Python is used to iterate over a sequence (such as a list, tuple, dictionary, set, or string) or other iterable objects.

Syntax
python
Copy code
for variable in sequence:
    # block of code
Example
python
Copy code
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)
Output:

Copy code
apple
banana
cherry
Example: Iterating Over a String
python
Copy code
for char in "Python":
    print(char)
Output:

css
Copy code
P
y
t
h
o
n
2. The while Loop
The while loop in Python repeatedly executes a block of code as long as a given condition is true.

Syntax
python
Copy code
while condition:
    # block of code
Example
python
Copy code
count = 1

while count <= 5:
    print(count)
    count += 1
Output:

Copy code
1
2
3
4
5
3. Controlling Loop Execution
Python provides several control statements to manage the flow of loops: break, continue, and else.

The break Statement
The break statement is used to exit the loop prematurely when a certain condition is met.

Example
python
Copy code
for num in range(1, 11):
    if num == 5:
        break
    print(num)
Output:

Copy code
1
2
3
4
The continue Statement
The continue statement skips the current iteration and moves to the next iteration of the loop.

Example
python
Copy code
for num in range(1, 11):
    if num % 2 == 0:
        continue
    print(num)
Output:

Copy code
1
3
5
7
9
The else Clause with Loops
The else clause can be used with loops to execute a block of code when the loop condition becomes false.

Example with for Loop
python
Copy code
for num in range(1, 6):
    print(num)
else:
    print("Loop completed successfully.")
Output:

vbnet
Copy code
1
2
3
4
5
Loop completed successfully.
Example with while Loop
python
Copy code
count = 1

while count <= 5:
    print(count)
    count += 1
else:
    print("Loop completed successfully.")
Output:

vbnet
Copy code
1
2
3
4
5
Loop completed successfully.
4. Nested Loops
You can use one loop inside another loop to create a nested loop. This is useful for working with multi-dimensional data structures, such as lists of lists.

Example
python
Copy code
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

for row in matrix:
    for element in row:
        print(element, end=" ")
    print()
Output:

Copy code
1 2 3 
4 5 6 
7 8 9 
Examples and Applications
To better understand repetitive structures, let's look at some practical examples.

Example 1: Summing Numbers from 1 to 100
python
Copy code
total = 0

for num in range(1, 101):
    total += num

print("Sum of numbers from 1 to 100:", total)
Output:

css
Copy code
Sum of numbers from 1 to 100: 5050
Example 2: Finding Prime Numbers Within a Range
python
Copy code
start = 10
end = 50

print("Prime numbers between", start, "and", end, "are:")

for num in range(start, end + 1):
    if num > 1:
        for i in range(2, num):
            if num % i == 0:
                break
        else:
            print(num)
Output:

sql
Copy code
Prime numbers between 10 and 50 are:
11
13
17
19
23
29
31
37
41
43
47
Example 3: Generating Multiplication Table
python
Copy code
num = 5

print("Multiplication Table for", num)

for i in range(1, 11):
    print(num, 'x', i, '=', num * i)
Output:

css
Copy code
Multiplication Table for 5
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
Summary
In this chapter, we've explored repetitive structures in Python, including for and while loops. We've discussed how to control the flow of loops using break, continue, and else statements. We've also covered nested loops and provided practical examples to illustrate the usage of loops in various scenarios. Understanding these looping constructs is essential for writing efficient and effective Python programs that perform repetitive tasks with ease.

