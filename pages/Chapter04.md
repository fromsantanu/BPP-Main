# Chapter: Repetitive Structures in Python
## Introduction
Repetitive structures, also known as loops, are fundamental in programming as they allow you to execute a block of code multiple times. In Python, the primary looping structures are for and while loops. This chapter will explore these loops, providing examples to illustrate their usage.

## 1. The for Loop
The for loop in Python is used to iterate over a sequence (such as a list, tuple, dictionary, set, or string) or other iterable objects.

#### Syntax
```python
for variable in sequence:
    # block of code
```

#### Example
```python
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)
```

##### Output:
```
apple
banana
cherry
```

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
