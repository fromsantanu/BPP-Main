Chapter 15: Chi-Square Tests
Overview of Chi-Square Tests
Chi-Square tests are statistical tests used to examine the relationships between categorical variables. They are used to determine if there is a significant association between variables or if a sample data matches a population. The two main types of Chi-Square tests are the Chi-Square Test for Independence and the Chi-Square Goodness-of-Fit Test.

Chi-Square Test for Independence
The Chi-Square Test for Independence is used to determine if there is a significant association between two categorical variables. It tests the null hypothesis that the variables are independent.

Example: Chi-Square Test for Independence
Let's use a hypothetical dataset to demonstrate the Chi-Square Test for Independence.

python
Copy code
import pandas as pd
import numpy as np
from scipy.stats import chi2_contingency

# Creating a sample dataset
data = {'Gender': ['Male', 'Male', 'Male', 'Female', 'Female', 'Female'],
        'Preference': ['A', 'B', 'A', 'B', 'A', 'B']}
df = pd.DataFrame(data)

# Creating a contingency table
contingency_table = pd.crosstab(df['Gender'], df['Preference'])
print("Contingency Table:")
print(contingency_table)

# Performing Chi-Square Test for Independence
chi2, p, dof, expected = chi2_contingency(contingency_table)
print(f"Chi-Square Test for Independence results: Chi2 = {chi2}, p-value = {p}, degrees of freedom = {dof}")
print("Expected frequencies:")
print(expected)
Chi-Square Goodness-of-Fit Test
The Chi-Square Goodness-of-Fit Test is used to determine if a sample data matches a population with a specific distribution. It tests the null hypothesis that the observed frequencies match the expected frequencies.

Example: Chi-Square Goodness-of-Fit Test
Let's use a hypothetical dataset to demonstrate the Chi-Square Goodness-of-Fit Test.

python
Copy code
from scipy.stats import chisquare

# Creating a sample dataset
observed_frequencies = [30, 25, 20, 25]
expected_frequencies = [25, 25, 25, 25]

# Performing Chi-Square Goodness-of-Fit Test
chi2, p = chisquare(observed_frequencies, expected_frequencies)
print(f"Chi-Square Goodness-of-Fit Test results: Chi2 = {chi2}, p-value = {p}")
Example: Complete Workflow
Here is a complete example that demonstrates performing the Chi-Square Test for Independence and the Chi-Square Goodness-of-Fit Test.

python
Copy code
import pandas as pd
import numpy as np
from scipy.stats import chi2_contingency, chisquare

# Chi-Square Test for Independence Example
# Creating a sample dataset
data_independence = {'Gender': ['Male', 'Male', 'Male', 'Female', 'Female', 'Female'],
                     'Preference': ['A', 'B', 'A', 'B', 'A', 'B']}
df_independence = pd.DataFrame(data_independence)

# Creating a contingency table
contingency_table_independence = pd.crosstab(df_independence['Gender'], df_independence['Preference'])
print("Contingency Table for Independence Test:")
print(contingency_table_independence)

# Performing Chi-Square Test for Independence
chi2_independence, p_independence, dof_independence, expected_independence = chi2_contingency(contingency_table_independence)
print(f"Chi-Square Test for Independence results: Chi2 = {chi2_independence}, p-value = {p_independence}, degrees of freedom = {dof_independence}")
print("Expected frequencies for Independence Test:")
print(expected_independence)

# Chi-Square Goodness-of-Fit Test Example
# Creating a sample dataset
observed_frequencies_gof = [30, 25, 20, 25]
expected_frequencies_gof = [25, 25, 25, 25]

# Performing Chi-Square Goodness-of-Fit Test
chi2_gof, p_gof = chisquare(observed_frequencies_gof, expected_frequencies_gof)
print(f"Chi-Square Goodness-of-Fit Test results: Chi2 = {chi2_gof}, p-value = {p_gof}")
In this chapter, we covered the basics of Chi-Square Tests, including the Chi-Square Test for Independence and the Chi-Square Goodness-of-Fit Test. We provided examples to demonstrate how to perform these tests using Python's scipy library and how to interpret the results.
