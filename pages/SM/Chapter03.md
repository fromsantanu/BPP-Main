# Chapter 3: Exploratory Data Analysis (EDA)

## Descriptive Statistics
Descriptive statistics summarize the main features of a dataset, providing simple summaries about the sample and the measures. This can be done using pandas' built-in functions.

### Summary Statistics
You can quickly get summary statistics for your DataFrame using the describe method.

```python
import pandas as pd

# Example DataFrame
data = {
    'A': [1, 2, 3, 4, 5],
    'B': [5, 4, 3, 2, 1],
    'C': [2, 3, 4, 5, 6]
}
df = pd.DataFrame(data)

# Summary statistics
print(df.describe())
```

### Individual Statistics
You can also calculate individual statistics such as mean, median, and standard deviation.

```python
# Mean
print(df.mean())

# Median
print(df.median())

# Standard Deviation
print(df.std())
```

Frequency Counts
For categorical data, you can use the value_counts method to get the frequency of each category.

python
Copy code
# Example categorical DataFrame
data = {
    'Category': ['A', 'B', 'A', 'C', 'B', 'A', 'C']
}
df = pd.DataFrame(data)

# Frequency counts
print(df['Category'].value_counts())
Data Visualization
Data visualization helps in understanding the distribution, trends, and patterns in your data. The matplotlib and seaborn libraries are commonly used for this purpose.

Histograms
Histograms are used to visualize the distribution of a single numerical variable.

python
Copy code
import matplotlib.pyplot as plt

# Example DataFrame
data = {
    'A': [1, 2, 3, 4, 5, 5, 5, 6, 6, 7, 8, 9, 10]
}
df = pd.DataFrame(data)

# Histogram
plt.hist(df['A'], bins=5)
plt.xlabel('Value')
plt.ylabel('Frequency')
plt.title('Histogram of A')
plt.show()
Box Plots
Box plots provide a summary of a set of data values, showing the median, quartiles, and outliers.

python
Copy code
# Box plot
plt.boxplot(df['A'])
plt.xlabel('A')
plt.title('Box Plot of A')
plt.show()
Scatter Plots
Scatter plots show the relationship between two numerical variables.

python
Copy code
# Example DataFrame
data = {
    'A': [1, 2, 3, 4, 5],
    'B': [5, 4, 3, 2, 1]
}
df = pd.DataFrame(data)

# Scatter plot
plt.scatter(df['A'], df['B'])
plt.xlabel('A')
plt.ylabel('B')
plt.title('Scatter Plot of A vs B')
plt.show()
Pair Plots
Pair plots are useful for visualizing relationships between multiple pairs of variables in a dataset.

python
Copy code
import seaborn as sns

# Example DataFrame
data = {
    'A': [1, 2, 3, 4, 5],
    'B': [5, 4, 3, 2, 1],
    'C': [2, 3, 4, 5, 6]
}
df = pd.DataFrame(data)

# Pair plot
sns.pairplot(df)
plt.show()
Correlation Analysis
Correlation analysis measures the relationship between two variables. The corr method in pandas calculates the correlation matrix, showing correlation coefficients between pairs of variables.

Correlation Matrix
python
Copy code
# Example DataFrame
data = {
    'A': [1, 2, 3, 4, 5],
    'B': [5, 4, 3, 2, 1],
    'C': [2, 3, 4, 5, 6]
}
df = pd.DataFrame(data)

# Correlation matrix
print(df.corr())
Heatmap of Correlation Matrix
A heatmap provides a visual representation of the correlation matrix, making it easier to identify strong correlations.

python
Copy code
# Heatmap
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.title('Correlation Matrix Heatmap')
plt.show()
Example: Complete Workflow
Here is a complete example that demonstrates descriptive statistics, data visualization, and correlation analysis.

python
Copy code
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Step 1: Creating an example DataFrame
data = {
    'A': [1, 2, 3, 4, 5, 5, 5, 6, 6, 7, 8, 9, 10],
    'B': [5, 4, 3, 2, 1, 2, 3, 4, 5, 6, 7, 8, 9],
    'C': [2, 3, 4, 5, 6, 5, 4, 3, 2, 1, 0, -1, -2]
}
df = pd.DataFrame(data)

# Step 2: Descriptive statistics
print("Descriptive Statistics:")
print(df.describe())

# Step 3: Histogram
plt.hist(df['A'], bins=5)
plt.xlabel('Value')
plt.ylabel('Frequency')
plt.title('Histogram of A')
plt.show()

# Step 4: Box plot
plt.boxplot(df['A'])
plt.xlabel('A')
plt.title('Box Plot of A')
plt.show()

# Step 5: Scatter plot
plt.scatter(df['A'], df['B'])
plt.xlabel('A')
plt.ylabel('B')
plt.title('Scatter Plot of A vs B')
plt.show()

# Step 6: Pair plot
sns.pairplot(df)
plt.show()

# Step 7: Correlation matrix
print("Correlation Matrix:")
print(df.corr())

# Step 8: Heatmap of the correlation matrix
sns.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.title('Correlation Matrix Heatmap')
plt.show()
In this chapter, we covered essential techniques for Exploratory Data Analysis (EDA), including descriptive statistics, data visualization, and correlation analysis. These tools help you understand your data better and prepare it for further analysis and modeling.
