Chapter 14: Non-Parametric Tests
Overview of Non-Parametric Tests
Non-parametric tests are statistical tests that do not assume a specific distribution for the data. They are used when the assumptions of parametric tests (e.g., normality) are not met. Non-parametric tests are particularly useful for ordinal data, ranks, or data that are not normally distributed.

Mann-Whitney U Test
The Mann-Whitney U test is used to determine if there is a significant difference between the distributions of two independent samples. It is the non-parametric equivalent of the two-sample t-test.

Example: Mann-Whitney U Test
python
Copy code
import numpy as np
from scipy.stats import mannwhitneyu

# Sample data
group1 = np.random.randn(30) + 2
group2 = np.random.randn(30) + 2.5

# Performing Mann-Whitney U test
u_stat, p_value = mannwhitneyu(group1, group2)
print(f"Mann-Whitney U test results: U-statistic = {u_stat}, p-value = {p_value}")
Wilcoxon Signed-Rank Test
The Wilcoxon signed-rank test is used to determine if there is a significant difference between the distributions of two related samples. It is the non-parametric equivalent of the paired t-test.

Example: Wilcoxon Signed-Rank Test
python
Copy code
from scipy.stats import wilcoxon

# Sample data
before_treatment = np.random.randn(30) + 2
after_treatment = before_treatment + np.random.randn(30) * 0.5

# Performing Wilcoxon signed-rank test
w_stat, p_value = wilcoxon(before_treatment, after_treatment)
print(f"Wilcoxon signed-rank test results: W-statistic = {w_stat}, p-value = {p_value}")
Kruskal-Wallis H Test
The Kruskal-Wallis H test is used to determine if there is a significant difference between the distributions of three or more independent samples. It is the non-parametric equivalent of the one-way ANOVA.

Example: Kruskal-Wallis H Test
python
Copy code
from scipy.stats import kruskal

# Sample data
group1 = np.random.randn(30) + 2
group2 = np.random.randn(30) + 2.5
group3 = np.random.randn(30) + 3

# Performing Kruskal-Wallis H test
h_stat, p_value = kruskal(group1, group2, group3)
print(f"Kruskal-Wallis H test results: H-statistic = {h_stat}, p-value = {p_value}")
Example: Complete Workflow
Here is a complete example that demonstrates performing the Mann-Whitney U test, Wilcoxon signed-rank test, and Kruskal-Wallis H test.

python
Copy code
import numpy as np
from scipy.stats import mannwhitneyu, wilcoxon, kruskal

# Mann-Whitney U Test Example
# Sample data
group1_mw = np.random.randn(30) + 2
group2_mw = np.random.randn(30) + 2.5

# Performing Mann-Whitney U test
u_stat_mw, p_value_mw = mannwhitneyu(group1_mw, group2_mw)
print(f"Mann-Whitney U test results: U-statistic = {u_stat_mw}, p-value = {p_value_mw}")

# Wilcoxon Signed-Rank Test Example
# Sample data
before_treatment_wsr = np.random.randn(30) + 2
after_treatment_wsr = before_treatment_wsr + np.random.randn(30) * 0.5

# Performing Wilcoxon signed-rank test
w_stat_wsr, p_value_wsr = wilcoxon(before_treatment_wsr, after_treatment_wsr)
print(f"Wilcoxon signed-rank test results: W-statistic = {w_stat_wsr}, p-value = {p_value_wsr}")

# Kruskal-Wallis H Test Example
# Sample data
group1_kw = np.random.randn(30) + 2
group2_kw = np.random.randn(30) + 2.5
group3_kw = np.random.randn(30) + 3

# Performing Kruskal-Wallis H test
h_stat_kw, p_value_kw = kruskal(group1_kw, group2_kw, group3_kw)
print(f"Kruskal-Wallis H test results: H-statistic = {h_stat_kw}, p-value = {p_value_kw}")
In this chapter, we covered the basics of non-parametric tests, including the Mann-Whitney U test, Wilcoxon signed-rank test, and Kruskal-Wallis H test. We provided examples to demonstrate how to perform these tests using Python's scipy library and how to interpret the results.
