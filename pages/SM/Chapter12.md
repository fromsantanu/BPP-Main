# Chapter 12: Factor Analysis

## Overview of Factor Analysis
Factor Analysis is a statistical technique used to identify underlying relationships between variables by grouping them into factors. It is widely used in fields like psychology, social sciences, and marketing to reduce the dimensionality of data.

## Exploratory Factor Analysis (EFA)
Exploratory Factor Analysis (EFA) is used to discover the underlying structure of a relatively large set of variables. It identifies the number of common factors influencing the data without imposing any preconceived structure on the outcome.

### Example: Exploratory Factor Analysis
Let's use a hypothetical dataset to demonstrate EFA using Python's factor_analyzer library.

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from factor_analyzer import FactorAnalyzer

# Creating a sample dataset
np.random.seed(0)
data = np.random.randn(100, 6)
df = pd.DataFrame(data, columns=['Feature1', 'Feature2', 'Feature3', 'Feature4', 'Feature5', 'Feature6'])

# Performing Exploratory Factor Analysis
fa = FactorAnalyzer(n_factors=2, rotation='varimax')
fa.fit(df)

# Getting the factor loadings
loadings = fa.loadings_
loadings_df = pd.DataFrame(loadings, index=df.columns, columns=['Factor1', 'Factor2'])
print(loadings_df)

# Visualizing the factor loadings
plt.matshow(loadings, cmap='viridis')
plt.colorbar()
plt.xticks(range(loadings_df.shape[1]), loadings_df.columns, rotation=90)
plt.yticks(range(loadings_df.shape[0]), loadings_df.index)
plt.title('Factor Loadings')
plt.show()
```

## Confirmatory Factor Analysis (CFA)
Confirmatory Factor Analysis (CFA) is used to test whether a hypothesized factor structure fits the observed data. It is often used in the later stages of research to confirm theories or models.

### Example: Confirmatory Factor Analysis
Let's use a hypothetical dataset to demonstrate CFA using Python's semopy library.

```python
import pandas as pd
import numpy as np
from semopy import Model, Optimizer

# Creating a sample dataset
np.random.seed(0)
data = np.random.randn(100, 6)
df = pd.DataFrame(data, columns=['Feature1', 'Feature2', 'Feature3', 'Feature4', 'Feature5', 'Feature6'])

# Defining the CFA model
model_desc = """
F1 =~ Feature1 + Feature2 + Feature3
F2 =~ Feature4 + Feature5 + Feature6
"""

# Performing Confirmatory Factor Analysis
model = Model(model_desc)
res = model.fit(df)

# Getting the factor loadings
loadings = model.inspect()
print(loadings)

# Visualizing the factor loadings
import seaborn as sns
sns.heatmap(loadings, annot=True, cmap='viridis')
plt.title('Factor Loadings')
plt.show()
```

## Example: Complete Workflow
Here is a complete example that demonstrates both Exploratory Factor Analysis (EFA) and Confirmatory Factor Analysis (CFA).

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from factor_analyzer import FactorAnalyzer
from semopy import Model, Optimizer
import seaborn as sns

# Exploratory Factor Analysis Example
# Creating a sample dataset
np.random.seed(0)
data_efa = np.random.randn(100, 6)
df_efa = pd.DataFrame(data_efa, columns=['Feature1', 'Feature2', 'Feature3', 'Feature4', 'Feature5', 'Feature6'])

# Performing Exploratory Factor Analysis
fa = FactorAnalyzer(n_factors=2, rotation='varimax')
fa.fit(df_efa)

# Getting the factor loadings
loadings_efa = fa.loadings_
loadings_df_efa = pd.DataFrame(loadings_efa, index=df_efa.columns, columns=['Factor1', 'Factor2'])
print("Exploratory Factor Analysis Loadings:")
print(loadings_df_efa)

# Visualizing the factor loadings
plt.matshow(loadings_efa, cmap='viridis')
plt.colorbar()
plt.xticks(range(loadings_df_efa.shape[1]), loadings_df_efa.columns, rotation=90)
plt.yticks(range(loadings_df_efa.shape[0]), loadings_df_efa.index)
plt.title('Factor Loadings (EFA)')
plt.show()

# Confirmatory Factor Analysis Example
# Creating a sample dataset
data_cfa = np.random.randn(100, 6)
df_cfa = pd.DataFrame(data_cfa, columns=['Feature1', 'Feature2', 'Feature3', 'Feature4', 'Feature5', 'Feature6'])

# Defining the CFA model
model_desc = """
F1 =~ Feature1 + Feature2 + Feature3
F2 =~ Feature4 + Feature5 + Feature6
"""

# Performing Confirmatory Factor Analysis
model = Model(model_desc)
res = model.fit(df_cfa)

# Getting the factor loadings
loadings_cfa = model.inspect()
print("Confirmatory Factor Analysis Loadings:")
print(loadings_cfa)

# Visualizing the factor loadings
sns.heatmap(loadings_cfa, annot=True, cmap='viridis')
plt.title('Factor Loadings (CFA)')
plt.show()
```

In this chapter, we covered the basics of Factor Analysis, including Exploratory Factor Analysis (EFA) and Confirmatory Factor Analysis (CFA). We provided examples to demonstrate how to perform these analyses using Python's factor_analyzer and semopy libraries and how to interpret the factor loadings.
