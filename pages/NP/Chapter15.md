Random Distributions
NumPy's random module provides functions to generate random numbers from a variety of probability distributions. This chapter covers some of the most commonly used random distributions: uniform, normal, binomial, and others.

Uniform Distribution
The uniform function generates random numbers from a uniform distribution over a specified interval [low, high).

Example
python
Copy code
import numpy as np

# Generating a single random number from a uniform distribution
uniform_single = np.random.uniform(low=0.0, high=1.0)
print("Single uniform random number:", uniform_single)

# Generating a 1D array of uniform random numbers
uniform_array_1d = np.random.uniform(low=0.0, high=1.0, size=5)
print("1D array of uniform random numbers:", uniform_array_1d)

# Generating a 2D array of uniform random numbers
uniform_array_2d = np.random.uniform(low=0.0, high=1.0, size=(3, 4))
print("2D array of uniform random numbers:\n", uniform_array_2d)
Normal Distribution
The normal function generates random numbers from a normal (Gaussian) distribution with a specified mean and standard deviation.

Example
python
Copy code
# Generating a single random number from a normal distribution
normal_single = np.random.normal(loc=0.0, scale=1.0)
print("Single normal random number:", normal_single)

# Generating a 1D array of normal random numbers
normal_array_1d = np.random.normal(loc=0.0, scale=1.0, size=5)
print("1D array of normal random numbers:", normal_array_1d)

# Generating a 2D array of normal random numbers
normal_array_2d = np.random.normal(loc=0.0, scale=1.0, size=(3, 4))
print("2D array of normal random numbers:\n", normal_array_2d)
Binomial Distribution
The binomial function generates random numbers from a binomial distribution with specified parameters n (number of trials) and p (probability of success).

Example
python
Copy code
# Generating a single random number from a binomial distribution
binomial_single = np.random.binomial(n=10, p=0.5)
print("Single binomial random number:", binomial_single)

# Generating a 1D array of binomial random numbers
binomial_array_1d = np.random.binomial(n=10, p=0.5, size=5)
print("1D array of binomial random numbers:", binomial_array_1d)

# Generating a 2D array of binomial random numbers
binomial_array_2d = np.random.binomial(n=10, p=0.5, size=(3, 4))
print("2D array of binomial random numbers:\n", binomial_array_2d)
Poisson Distribution
The poisson function generates random numbers from a Poisson distribution with a specified lambda parameter (rate or average number of events).

Example
python
Copy code
# Generating a single random number from a Poisson distribution
poisson_single = np.random.poisson(lam=3.0)
print("Single Poisson random number:", poisson_single)

# Generating a 1D array of Poisson random numbers
poisson_array_1d = np.random.poisson(lam=3.0, size=5)
print("1D array of Poisson random numbers:", poisson_array_1d)

# Generating a 2D array of Poisson random numbers
poisson_array_2d = np.random.poisson(lam=3.0, size=(3, 4))
print("2D array of Poisson random numbers:\n", poisson_array_2d)
Exponential Distribution
The exponential function generates random numbers from an exponential distribution with a specified scale parameter (inverse of the rate).

Example
python
Copy code
# Generating a single random number from an exponential distribution
exponential_single = np.random.exponential(scale=1.0)
print("Single exponential random number:", exponential_single)

# Generating a 1D array of exponential random numbers
exponential_array_1d = np.random.exponential(scale=1.0, size=5)
print("1D array of exponential random numbers:", exponential_array_1d)

# Generating a 2D array of exponential random numbers
exponential_array_2d = np.random.exponential(scale=1.0, size=(3, 4))
print("2D array of exponential random numbers:\n", exponential_array_2d)
Example Code
Here are comprehensive examples demonstrating the use of random distributions:

python
Copy code
import numpy as np

# Uniform distribution
uniform_single = np.random.uniform(low=0.0, high=1.0)
print("Single uniform random number:", uniform_single)

uniform_array_1d = np.random.uniform(low=0.0, high=1.0, size=5)
print("1D array of uniform random numbers:", uniform_array_1d)

uniform_array_2d = np.random.uniform(low=0.0, high=1.0, size=(3, 4))
print("2D array of uniform random numbers:\n", uniform_array_2d)

# Normal distribution
normal_single = np.random.normal(loc=0.0, scale=1.0)
print("Single normal random number:", normal_single)

normal_array_1d = np.random.normal(loc=0.0, scale=1.0, size=5)
print("1D array of normal random numbers:", normal_array_1d)

normal_array_2d = np.random.normal(loc=0.0, scale=1.0, size=(3, 4))
print("2D array of normal random numbers:\n", normal_array_2d)

# Binomial distribution
binomial_single = np.random.binomial(n=10, p=0.5)
print("Single binomial random number:", binomial_single)

binomial_array_1d = np.random.binomial(n=10, p=0.5, size=5)
print("1D array of binomial random numbers:", binomial_array_1d)

binomial_array_2d = np.random.binomial(n=10, p=0.5, size=(3, 4))
print("2D array of binomial random numbers:\n", binomial_array_2d)

# Poisson distribution
poisson_single = np.random.poisson(lam=3.0)
print("Single Poisson random number:", poisson_single)

poisson_array_1d = np.random.poisson(lam=3.0, size=5)
print("1D array of Poisson random numbers:", poisson_array_1d)

poisson_array_2d = np.random.poisson(lam=3.0, size=(3, 4))
print("2D array of Poisson random numbers:\n", poisson_array_2d)

# Exponential distribution
exponential_single = np.random.exponential(scale=1.0)
print("Single exponential random number:", exponential_single)

exponential_array_1d = np.random.exponential(scale=1.0, size=5)
print("1D array of exponential random numbers:", exponential_array_1d)

exponential_array_2d = np.random.exponential(scale=1.0, size=(3, 4))
print("2D array of exponential random numbers:\n", exponential_array_2d)
By understanding and using these random distribution functions, you can effectively perform simulations, random sampling, and various probabilistic computations in NumPy, enabling deeper analysis and modeling of data.
