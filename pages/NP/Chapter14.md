# Random Number Generation
NumPy provides a robust module for random number generation, which is essential for simulations, random sampling, and probabilistic algorithms. The np.random module includes functions for generating random numbers from various distributions. This chapter covers some of the most commonly used functions: rand, randn, randint, seed, and choice.

## np.random.rand
The rand function generates random numbers from a uniform distribution over [0, 1).

### Example
```python
import numpy as np

# Generating a single random number
random_number = np.random.rand()
print("Single random number:", random_number)

# Generating a 1D array of random numbers
random_array_1d = np.random.rand(5)
print("1D array of random numbers:", random_array_1d)

# Generating a 2D array of random numbers
random_array_2d = np.random.rand(3, 4)
print("2D array of random numbers:\n", random_array_2d)
```

## np.random.randn
The randn function generates random numbers from a standard normal distribution (mean = 0, standard deviation = 1).

### Example
```python
# Generating a single random number from a standard normal distribution
random_number_normal = np.random.randn()
print("Single random number from normal distribution:", random_number_normal)

# Generating a 1D array of random numbers from a standard normal distribution
random_array_1d_normal = np.random.randn(5)
print("1D array of random numbers from normal distribution:", random_array_1d_normal)

# Generating a 2D array of random numbers from a standard normal distribution
random_array_2d_normal = np.random.randn(3, 4)
print("2D array of random numbers from normal distribution:\n", random_array_2d_normal)
```

## np.random.randint
The randint function generates random integers from a specified range.

### Example
```python
# Generating a single random integer between 0 and 10
random_integer = np.random.randint(0, 10)
print("Single random integer:", random_integer)

# Generating a 1D array of random integers between 0 and 10
random_array_1d_int = np.random.randint(0, 10, size=5)
print("1D array of random integers:", random_array_1d_int)

# Generating a 2D array of random integers between 0 and 10
random_array_2d_int = np.random.randint(0, 10, size=(3, 4))
print("2D array of random integers:\n", random_array_2d_int)
```

## np.random.seed
The seed function sets the seed for the random number generator, ensuring reproducibility of random number sequences.

### Example
```python
# Setting the seed
np.random.seed(42)

# Generating random numbers with the set seed
random_number_seed = np.random.rand()
print("Random number with seed 42:", random_number_seed)

# Resetting the seed and generating the same random numbers
np.random.seed(42)
random_number_seed_repeat = np.random.rand()
print("Random number with seed 42 (repeated):", random_number_seed_repeat)
```

## np.random.choice
The choice function generates a random sample from a given 1D array.

### Example
```python
# Creating an array to sample from
array = np.array([10, 20, 30, 40, 50])

# Randomly selecting a single element from the array
random_choice_single = np.random.choice(array)
print("Randomly selected element:", random_choice_single)

# Randomly selecting multiple elements with replacement
random_choice_multiple = np.random.choice(array, size=3)
print("Randomly selected multiple elements with replacement:", random_choice_multiple)

# Randomly selecting multiple elements without replacement
random_choice_multiple_no_replace = np.random.choice(array, size=3, replace=False)
print("Randomly selected multiple elements without replacement:", random_choice_multiple_no_replace)
```

## Example Code
Here are comprehensive examples demonstrating the use of rand, randn, randint, seed, and choice:

```python
import numpy as np

# np.random.rand
random_number = np.random.rand()
print("Single random number:", random_number)

random_array_1d = np.random.rand(5)
print("1D array of random numbers:", random_array_1d)

random_array_2d = np.random.rand(3, 4)
print("2D array of random numbers:\n", random_array_2d)

# np.random.randn
random_number_normal = np.random.randn()
print("Single random number from normal distribution:", random_number_normal)

random_array_1d_normal = np.random.randn(5)
print("1D array of random numbers from normal distribution:", random_array_1d_normal)

random_array_2d_normal = np.random.randn(3, 4)
print("2D array of random numbers from normal distribution:\n", random_array_2d_normal)

# np.random.randint
random_integer = np.random.randint(0, 10)
print("Single random integer:", random_integer)

random_array_1d_int = np.random.randint(0, 10, size=5)
print("1D array of random integers:", random_array_1d_int)

random_array_2d_int = np.random.randint(0, 10, size=(3, 4))
print("2D array of random integers:\n", random_array_2d_int)

# np.random.seed
np.random.seed(42)
random_number_seed = np.random.rand()
print("Random number with seed 42:", random_number_seed)

np.random.seed(42)
random_number_seed_repeat = np.random.rand()
print("Random number with seed 42 (repeated):", random_number_seed_repeat)

# np.random.choice
array = np.array([10, 20, 30, 40, 50])
random_choice_single = np.random.choice(array)
print("Randomly selected element:", random_choice_single)

random_choice_multiple = np.random.choice(array, size=3)
print("Randomly selected multiple elements with replacement:", random_choice_multiple)

random_choice_multiple_no_replace = np.random.choice(array, size=3, replace=False)
print("Randomly selected multiple elements without replacement:", random_choice_multiple_no_replace)
```

By understanding and using these random number generation functions, you can effectively perform simulations, random sampling, and various probabilistic computations in NumPy.
