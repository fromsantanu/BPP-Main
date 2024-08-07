Chapter 10: Bayesian Analysis
## Overview of Bayesian Analysis

Bayesian analysis is a statistical paradigm that involves updating the probability of a hypothesis as more evidence or information becomes available. It is based on Bayes' theorem:

$\[ P(\theta | D) = \frac{P(D | \theta) P(\theta)}{P(D)} \]$

Where:
- $\( P(\theta | D) \)$ is the posterior probability of the parameters given the data.
- $\( P(D | \theta) \)$ is the likelihood of the data given the parameters.
- $\( P(\theta) \)$ is the prior probability of the parameters.
- $\( P(D) \)$ is the marginal likelihood or evidence.

Bayesian Linear Regression
Bayesian linear regression extends traditional linear regression by treating the model parameters as random variables with specified prior distributions.

Example: Bayesian Linear Regression
Let's use a hypothetical dataset to demonstrate Bayesian linear regression using the PyMC3 library.

python
Copy code
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import pymc3 as pm

# Creating a sample dataset
np.random.seed(0)
X = np.random.randn(100)
Y = 2.5 * X + np.random.randn(100) * 0.5
df = pd.DataFrame({'X': X, 'Y': Y})

# Visualizing the data
plt.scatter(df['X'], df['Y'])
plt.xlabel('X')
plt.ylabel('Y')
plt.title('Scatter Plot of Y vs X')
plt.show()

# Bayesian Linear Regression
with pm.Model() as model:
    # Priors for unknown model parameters
    alpha = pm.Normal('alpha', mu=0, sigma=10)
    beta = pm.Normal('beta', mu=0, sigma=10)
    sigma = pm.HalfNormal('sigma', sigma=1)

    # Expected value of outcome
    mu = alpha + beta * df['X']

    # Likelihood (sampling distribution) of observations
    Y_obs = pm.Normal('Y_obs', mu=mu, sigma=sigma, observed=df['Y'])

    # Posterior sampling
    trace = pm.sample(1000, return_inferencedata=False)

# Summary of the posterior distribution
print(pm.summary(trace))

# Plotting the posterior distributions
pm.plot_posterior(trace)
plt.show()
Bayesian Hierarchical Models
Bayesian hierarchical models are used when data is collected at different levels of hierarchy. These models account for variability at each level.

Example: Bayesian Hierarchical Model
Let's use a hypothetical dataset to demonstrate a Bayesian hierarchical model using the PyMC3 library.

python
Copy code
# Creating a sample dataset
np.random.seed(0)
group1 = np.random.normal(5, 1, 50)
group2 = np.random.normal(7, 1, 50)
group3 = np.random.normal(9, 1, 50)
groups = np.concatenate([group1, group2, group3])
group_labels = np.repeat(['A', 'B', 'C'], 50)
df = pd.DataFrame({'Value': groups, 'Group': group_labels})

# Visualizing the data
sns.boxplot(x='Group', y='Value', data=df)
plt.title('Box Plot of Values by Group')
plt.show()

# Bayesian Hierarchical Model
with pm.Model() as hierarchical_model:
    # Priors for group means
    group_means = pm.Normal('group_means', mu=0, sigma=10, shape=3)
    group_sd = pm.HalfNormal('group_sd', sigma=1)

    # Priors for individual observations
    y = pm.Normal('y', mu=group_means[df['Group'].cat.codes], sigma=group_sd, observed=df['Value'])

    # Posterior sampling
    trace_hierarchical = pm.sample(1000, return_inferencedata=False)

# Summary of the posterior distribution
print(pm.summary(trace_hierarchical))

# Plotting the posterior distributions
pm.plot_posterior(trace_hierarchical)
plt.show()
Example: Complete Workflow
Here is a complete example that demonstrates Bayesian linear regression and a Bayesian hierarchical model.

python
Copy code
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import pymc3 as pm
import seaborn as sns

# Bayesian Linear Regression Example
# Creating a sample dataset
np.random.seed(0)
X = np.random.randn(100)
Y = 2.5 * X + np.random.randn(100) * 0.5
df_linear = pd.DataFrame({'X': X, 'Y': Y})

# Visualizing the data
plt.scatter(df_linear['X'], df_linear['Y'])
plt.xlabel('X')
plt.ylabel('Y')
plt.title('Scatter Plot of Y vs X (Bayesian Linear Regression)')
plt.show()

# Bayesian Linear Regression
with pm.Model() as model_linear:
    # Priors for unknown model parameters
    alpha = pm.Normal('alpha', mu=0, sigma=10)
    beta = pm.Normal('beta', mu=0, sigma=10)
    sigma = pm.HalfNormal('sigma', sigma=1)

    # Expected value of outcome
    mu = alpha + beta * df_linear['X']

    # Likelihood (sampling distribution) of observations
    Y_obs = pm.Normal('Y_obs', mu=mu, sigma=sigma, observed=df_linear['Y'])

    # Posterior sampling
    trace_linear = pm.sample(1000, return_inferencedata=False)

print("Bayesian Linear Regression Summary:")
print(pm.summary(trace_linear))
pm.plot_posterior(trace_linear)
plt.show()

# Bayesian Hierarchical Model Example
# Creating a sample dataset
group1 = np.random.normal(5, 1, 50)
group2 = np.random.normal(7, 1, 50)
group3 = np.random.normal(9, 1, 50)
groups = np.concatenate([group1, group2, group3])
group_labels = np.repeat(['A', 'B', 'C'], 50)
df_hierarchical = pd.DataFrame({'Value': groups, 'Group': group_labels})

# Visualizing the data
sns.boxplot(x='Group', y='Value', data=df_hierarchical)
plt.title('Box Plot of Values by Group (Bayesian Hierarchical Model)')
plt.show()

# Bayesian Hierarchical Model
with pm.Model() as hierarchical_model:
    # Priors for group means
    group_means = pm.Normal('group_means', mu=0, sigma=10, shape=3)
    group_sd = pm.HalfNormal('group_sd', sigma=1)

    # Priors for individual observations
    y = pm.Normal('y', mu=group_means[df_hierarchical['Group'].astype('category').cat.codes], sigma=group_sd, observed=df_hierarchical['Value'])

    # Posterior sampling
    trace_hierarchical = pm.sample(1000, return_inferencedata=False)

print("Bayesian Hierarchical Model Summary:")
print(pm.summary(trace_hierarchical))
pm.plot_posterior(trace_hierarchical)
plt.show()
In this chapter, we covered the basics of Bayesian analysis, including Bayesian linear regression and Bayesian hierarchical models. We provided examples to demonstrate how to perform these analyses using Python's PyMC3 library and how to interpret the results.
