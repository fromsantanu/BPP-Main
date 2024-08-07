Chapter 6: Analysis of Variance (ANOVA)
Overview of ANOVA
Analysis of Variance (ANOVA) is a statistical method used to compare the means of three or more groups to determine if at least one of the group means is significantly different from the others. ANOVA helps in understanding the influence of one or more categorical independent variables on a continuous dependent variable.

Types of ANOVA
One-Way ANOVA: Compares the means of three or more independent groups based on one factor.
Two-Way ANOVA: Compares the means based on two factors and can include interaction effects.
One-Way ANOVA
Example: Comparing Means of Three Groups
Let's use a hypothetical dataset to demonstrate one-way ANOVA.

python
Copy code
import pandas as pd
import numpy as np
import statsmodels.api as sm
from statsmodels.formula.api import ols
import matplotlib.pyplot as plt
import seaborn as sns

# Example dataset
data = {
    'Group': np.repeat(['A', 'B', 'C'], 10),
    'Value': np.random.randn(30) + np.repeat([0, 1, 2], 10)
}
df = pd.DataFrame(data)

# Box plot to visualize the groups
sns.boxplot(x='Group', y='Value', data=df)
plt.title('Box Plot of Groups')
plt.show()

# Performing one-way ANOVA
model = ols('Value ~ Group', data=df).fit()
anova_table = sm.stats.anova_lm(model, typ=2)
print(anova_table)
Two-Way ANOVA
Example: Comparing Means Based on Two Factors
Let's use a hypothetical dataset to demonstrate two-way ANOVA.

python
Copy code
# Example dataset
data = {
    'Factor1': np.repeat(['A', 'B'], 15),
    'Factor2': np.tile(['X', 'Y', 'Z'], 10),
    'Value': np.random.randn(30) + np.repeat([0, 1], 15) + np.tile([0, 1, 2], 10)
}
df = pd.DataFrame(data)

# Box plot to visualize the interaction between factors
sns.boxplot(x='Factor2', y='Value', hue='Factor1', data=df)
plt.title('Box Plot of Factors')
plt.show()

# Performing two-way ANOVA
model = ols('Value ~ Factor1 * Factor2', data=df).fit()
anova_table = sm.stats.anova_lm(model, typ=2)
print(anova_table)
Interpreting ANOVA Results
One-Way ANOVA Interpretation
The output of the one-way ANOVA provides an ANOVA table with the following columns:

sum_sq: Sum of squares.
df: Degrees of freedom.
F: F-statistic.
PR(>F): P-value of the F-statistic.
Interpret the p-value to determine if there is a statistically significant difference between the groups. A p-value less than 0.05 typically indicates significant differences.

Two-Way ANOVA Interpretation
The output of the two-way ANOVA provides an ANOVA table with the following columns:

sum_sq: Sum of squares.
df: Degrees of freedom.
F: F-statistic.
PR(>F): P-value of the F-statistic.
The table will include rows for each main effect (Factor1 and Factor2) and the interaction effect (Factor1
). Interpret the p-values to determine if there are significant main effects or interaction effects.

Example: Complete Workflow
Here is a complete example that demonstrates one-way ANOVA, two-way ANOVA, and interpretation of results.

python
Copy code
import pandas as pd
import numpy as np
import statsmodels.api as sm
from statsmodels.formula.api import ols
import matplotlib.pyplot as plt
import seaborn as sns

# One-Way ANOVA Example
# Example dataset
data_one_way = {
    'Group': np.repeat(['A', 'B', 'C'], 10),
    'Value': np.random.randn(30) + np.repeat([0, 1, 2], 10)
}
df_one_way = pd.DataFrame(data_one_way)

# Box plot to visualize the groups
sns.boxplot(x='Group', y='Value', data=df_one_way)
plt.title('Box Plot of Groups (One-Way ANOVA)')
plt.show()

# Performing one-way ANOVA
model_one_way = ols('Value ~ Group', data=df_one_way).fit()
anova_table_one_way = sm.stats.anova_lm(model_one_way, typ=2)
print("One-Way ANOVA Table:")
print(anova_table_one_way)

# Two-Way ANOVA Example
# Example dataset
data_two_way = {
    'Factor1': np.repeat(['A', 'B'], 15),
    'Factor2': np.tile(['X', 'Y', 'Z'], 10),
    'Value': np.random.randn(30) + np.repeat([0, 1], 15) + np.tile([0, 1, 2], 10)
}
df_two_way = pd.DataFrame(data_two_way)

# Box plot to visualize the interaction between factors
sns.boxplot(x='Factor2', y='Value', hue='Factor1', data=df_two_way)
plt.title('Box Plot of Factors (Two-Way ANOVA)')
plt.show()

# Performing two-way ANOVA
model_two_way = ols('Value ~ Factor1 * Factor2', data=df_two_way).fit()
anova_table_two_way = sm.stats.anova_lm(model_two_way, typ=2)
print("Two-Way ANOVA Table:")
print(anova_table_two_way)
In this chapter, we covered the basics of Analysis of Variance (ANOVA), including one-way ANOVA and two-way ANOVA. We provided examples to demonstrate how to perform these analyses using Python's statsmodels library and how to interpret the results.
