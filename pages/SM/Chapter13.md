# Chapter 13: Parametric Tests

## Overview of Parametric Tests
Parametric tests are statistical tests that assume the underlying data follows a specific distribution, typically the normal distribution. These tests are used to compare means, variances, and other parameters between groups.

## T-tests
T-tests are used to determine if there are significant differences between the means of two groups. There are three main types of t-tests: one-sample t-test, two-sample t-test (independent), and paired t-test.

### One-sample T-test
The one-sample t-test is used to determine if the mean of a single group is significantly different from a known or hypothesized value.

#### Example: One-sample T-test
```python
import numpy as np
from scipy import stats

# Sample data
np.random.seed(0)
data = np.random.randn(30) + 2

# Performing one-sample t-test
t_stat, p_value = stats.ttest_1samp(data, popmean=2)
print(f"One-sample t-test results: t-statistic = {t_stat}, p-value = {p_value}")
```

### Two-sample T-test (Independent)
The two-sample t-test is used to determine if the means of two independent groups are significantly different.

#### Example: Two-sample T-test
```python
# Sample data
group1 = np.random.randn(30) + 2
group2 = np.random.randn(30) + 2.5

# Performing two-sample t-test
t_stat, p_value = stats.ttest_ind(group1, group2)
print(f"Two-sample t-test results: t-statistic = {t_stat}, p-value = {p_value}")
```

### Paired T-test
The paired t-test is used to determine if the means of two related groups are significantly different.

#### Example: Paired T-test
```python
# Sample data
before_treatment = np.random.randn(30) + 2
after_treatment = before_treatment + np.random.randn(30) * 0.5

# Performing paired t-test
t_stat, p_value = stats.ttest_rel(before_treatment, after_treatment)
print(f"Paired t-test results: t-statistic = {t_stat}, p-value = {p_value}")
```

## Z-tests
Z-tests are used to determine if there are significant differences between means, typically for larger sample sizes (n > 30). Z-tests assume the data follows a normal distribution and that the population variance is known.

### One-sample Z-test
The one-sample Z-test is used to determine if the mean of a single group is significantly different from a known or hypothesized value.

#### Example: One-sample Z-test
```python
import numpy as np
from statsmodels.stats.weightstats import ztest

# Sample data
np.random.seed(0)
data = np.random.randn(50) + 2

# Performing one-sample z-test
z_stat, p_value = ztest(data, value=2)
print(f"One-sample Z-test results: z-statistic = {z_stat}, p-value = {p_value}")
```

### Two-sample Z-test (Independent)
The two-sample Z-test is used to determine if the means of two independent groups are significantly different.

#### Example: Two-sample Z-test

```python
# Sample data
group1 = np.random.randn(50) + 2
group2 = np.random.randn(50) + 2.5

# Performing two-sample z-test
z_stat, p_value = ztest(group1, group2)
print(f"Two-sample Z-test results: z-statistic = {z_stat}, p-value = {p_value}")
```

## Example: Complete Workflow
Here is a complete example that demonstrates performing one-sample t-test, two-sample t-test, paired t-test, one-sample Z-test, and two-sample Z-test.

```python
import numpy as np
from scipy import stats
from statsmodels.stats.weightstats import ztest

# One-sample T-test Example
# Sample data
np.random.seed(0)
data_one_sample = np.random.randn(30) + 2

# Performing one-sample t-test
t_stat_one_sample, p_value_one_sample = stats.ttest_1samp(data_one_sample, popmean=2)
print(f"One-sample T-test results: t-statistic = {t_stat_one_sample}, p-value = {p_value_one_sample}")

# Two-sample T-test Example
# Sample data
group1_two_sample = np.random.randn(30) + 2
group2_two_sample = np.random.randn(30) + 2.5

# Performing two-sample t-test
t_stat_two_sample, p_value_two_sample = stats.ttest_ind(group1_two_sample, group2_two_sample)
print(f"Two-sample T-test results: t-statistic = {t_stat_two_sample}, p-value = {p_value_two_sample}")

# Paired T-test Example
# Sample data
before_treatment_paired = np.random.randn(30) + 2
after_treatment_paired = before_treatment_paired + np.random.randn(30) * 0.5

# Performing paired t-test
t_stat_paired, p_value_paired = stats.ttest_rel(before_treatment_paired, after_treatment_paired)
print(f"Paired T-test results: t-statistic = {t_stat_paired}, p-value = {p_value_paired}")

# One-sample Z-test Example
# Sample data
data_one_sample_z = np.random.randn(50) + 2

# Performing one-sample z-test
z_stat_one_sample, p_value_one_sample = ztest(data_one_sample_z, value=2)
print(f"One-sample Z-test results: z-statistic = {z_stat_one_sample}, p-value = {p_value_one_sample}")

# Two-sample Z-test Example
# Sample data
group1_two_sample_z = np.random.randn(50) + 2
group2_two_sample_z = np.random.randn(50) + 2.5

# Performing two-sample z-test
z_stat_two_sample, p_value_two_sample = ztest(group1_two_sample_z, group2_two_sample_z)
print(f"Two-sample Z-test results: z-statistic = {z_stat_two_sample}, p-value = {p_value_two_sample}")
```

In this chapter, we covered the basics of parametric tests, including T-tests (one-sample, two-sample, paired) and Z-tests. We provided examples to demonstrate how to perform these tests using Python's scipy and statsmodels libraries and how to interpret the results.
