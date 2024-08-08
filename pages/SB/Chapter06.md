# Regression and Statistical Plots
Regression and statistical plots are essential for understanding relationships between variables and fitting models to data. Seaborn provides several functions to create regression plots and visualize statistical relationships. In this chapter, we will explore linear regression plots with lmplot, residual plots, logistic regression plots, and other ways to visualize statistical relationships.

## Linear Regression with lmplot
The lmplot function in Seaborn is used to plot linear relationships between variables. It fits and visualizes a linear regression model for the data.

### Basic Linear Regression
```python
import seaborn as sns
import matplotlib.pyplot as plt

# Load the tips dataset
tips = sns.load_dataset("tips")

# Create a linear regression plot
sns.lmplot(data=tips, x="total_bill", y="tip")
plt.title("Linear Regression of Tip vs Total Bill")
plt.show()
```

### Linear Regression with Multiple Facets
You can use the col and row parameters to create multiple subplots based on categorical variables.

```python
# Create a linear regression plot with multiple facets
sns.lmplot(data=tips, x="total_bill", y="tip", hue="sex", col="day", aspect=0.6, height=4)
plt.suptitle("Linear Regression of Tip vs Total Bill by Day and Sex", y=1.05)
plt.show()
```

## Residual and Logistic Regression Plots
### Residual Plots
Residual plots display the residuals of a regression model, which are the differences between the observed and predicted values. This helps in diagnosing the fit of the model.

```python
# Create a residual plot
sns.residplot(data=tips, x="total_bill", y="tip", lowess=True)
plt.title("Residual Plot of Tip vs Total Bill")
plt.show()
```

### Logistic Regression Plots
Logistic regression is used when the dependent variable is binary. Seaborn can be used to visualize logistic regression models.

```python
# Load the Titanic dataset
titanic = sns.load_dataset("titanic")

# Create a logistic regression plot
sns.lmplot(data=titanic, x="age", y="survived", logistic=True)
plt.title("Logistic Regression of Survival vs Age")
plt.show()
```

## Visualizing Statistical Relationships
Seaborn offers various functions to visualize statistical relationships, including joint plots and pair plots, which combine multiple types of plots.

### Joint Plots
Joint plots combine scatter plots with histograms or KDE plots to show bivariate relationships along with marginal distributions.

```python
# Create a joint plot with scatter and histograms
sns.jointplot(data=tips, x="total_bill", y="tip", kind="reg")
plt.suptitle("Joint Plot of Total Bill and Tip with Regression Line", y=1.02)
plt.show()
```

### Pair Plots
Pair plots display pairwise relationships between variables in a dataset and are useful for exploring relationships and distributions simultaneously.

```python
# Load the iris dataset
iris = sns.load_dataset("iris")

# Create a pair plot with regression lines
sns.pairplot(iris, hue="species", kind="reg")
plt.suptitle("Pair Plot of Iris Dataset with Regression Lines", y=1.02)
plt.show()
```

## Advanced Regression Plot Customizations
Seaborn allows for advanced customizations of regression plots to better understand the data and the model fit.

```python
# Create a linear regression plot with customizations
sns.lmplot(data=tips, x="total_bill", y="tip", hue="sex", markers=["o", "x"], palette="Set1", scatter_kws={'s':50, 'alpha':0.7})
plt.title("Customized Linear Regression of Tip vs Total Bill by Sex")
plt.show()
```
In this example, we customized the markers, palette, and scatter plot properties.

## Example: Combining Regression and Residual Plots
Let's combine linear regression and residual plots to get a comprehensive understanding of the model fit.

```python
# Create a figure with subplots
fig, ax = plt.subplots(1, 2, figsize=(14, 6))

# Linear regression plot
sns.regplot(data=tips, x="total_bill", y="tip", ax=ax[0])
ax[0].set_title("Linear Regression of Tip vs Total Bill")

# Residual plot
sns.residplot(data=tips, x="total_bill", y="tip", lowess=True, ax=ax[1])
ax[1].set_title("Residual Plot of Tip vs Total Bill")

plt.tight_layout()
plt.show()
```

## Conclusion
Seaborn's regression and statistical plots provide powerful tools for visualizing relationships between variables and fitting models to data. The lmplot function, along with residual and logistic regression plots, allows for detailed analysis and diagnosis of model fits. By leveraging these tools, you can create detailed and informative visualizations to enhance your data analysis and statistical understanding.
