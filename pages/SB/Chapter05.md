# Distribution Plots
Distribution plots are essential for understanding the underlying distribution of a dataset. Seaborn provides a variety of tools to visualize distributions, including histograms, KDE plots, rug plots, ECDF plots, joint plots, and pair plots. This chapter will explore these plots with code examples.

## Histograms and KDE Plots
### Histograms
Histograms display the distribution of a single variable by dividing the data into bins and counting the number of observations in each bin.

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Load the tips dataset
tips = sns.load_dataset("tips")

# Create a histogram
sns.histplot(data=tips, x="total_bill", bins=20, kde=True)
plt.title("Histogram of Total Bill with KDE")
plt.show()
```

### KDE Plots
Kernel Density Estimation (KDE) plots show the distribution of a variable by smoothing the observations with a Gaussian kernel.

```python
# Create a KDE plot
sns.kdeplot(data=tips, x="total_bill", shade=True)
plt.title("KDE Plot of Total Bill")
plt.show()
```

## Rug and ECDF Plots
### Rug Plots
Rug plots display individual observations along the axis, providing a way to visualize the distribution of data points.

```python
# Create a rug plot
sns.rugplot(data=tips, x="total_bill")
plt.title("Rug Plot of Total Bill")
plt.show()
```

### ECDF Plots
Empirical Cumulative Distribution Function (ECDF) plots show the proportion of data points that are less than or equal to a given value.

```python
# Create an ECDF plot
sns.ecdfplot(data=tips, x="total_bill")
plt.title("ECDF Plot of Total Bill")
plt.show()
```

## Joint and Pair Plots
### Joint Plots
Joint plots display the relationship between two variables and their individual distributions. Seaborn provides several types of joint plots, including scatter, hex, and KDE.

```python
# Create a joint plot with scatter and histograms
sns.jointplot(data=tips, x="total_bill", y="tip", kind="scatter")
plt.suptitle("Joint Plot of Total Bill and Tip", y=1.02)
plt.show()

# Create a joint plot with KDE
sns.jointplot(data=tips, x="total_bill", y="tip", kind="kde")
plt.suptitle("KDE Joint Plot of Total Bill and Tip", y=1.02)
plt.show()
```

### Pair Plots
Pair plots display pairwise relationships between variables in a dataset. They are useful for exploring relationships and distributions simultaneously.

```python
# Load the iris dataset
iris = sns.load_dataset("iris")

# Create a pair plot
sns.pairplot(iris, hue="species")
plt.suptitle("Pair Plot of Iris Dataset", y=1.02)
plt.show()
```

## Combining Plots
Seaborn allows you to combine different types of plots to create more informative visualizations. For example, you can combine histograms with KDE plots or use joint plots to show scatter plots with marginal histograms.

```python
# Combine histogram and KDE plot
sns.histplot(data=tips, x="total_bill", bins=20, kde=True)
sns.kdeplot(data=tips, x="total_bill", color="red", lw=2)
plt.title("Combined Histogram and KDE Plot of Total Bill")
plt.show()

# Combine joint plot with scatter and KDE
sns.jointplot(data=tips, x="total_bill", y="tip", kind="scatter", marginal_kws=dict(bins=20, fill=True))
plt.suptitle("Combined Scatter and KDE Joint Plot of Total Bill and Tip", y=1.02)
plt.show()
```

## Conclusion
Distribution plots in Seaborn offer a powerful set of tools for visualizing and understanding the distribution of data. Histograms, KDE plots, rug plots, ECDF plots, joint plots, and pair plots each provide unique insights into the distribution and relationships within your data. By combining these plots and customizing them, you can create detailed and informative visualizations that enhance your data analysis.
