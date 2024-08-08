# Dataset and Themes
Seaborn provides a range of built-in datasets that you can use to practice and create various visualizations. It also offers a variety of themes and aesthetic styles to enhance the appearance of your plots. In this chapter, we'll explore how to use these built-in datasets and customize the appearance of your plots using Seaborn's themes and styles.

## Built-in Datasets
Seaborn includes several built-in datasets that are useful for practicing data visualization. These datasets are easy to load and use directly in your code. Here are a few examples:

### Loading Built-in Datasets

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Load the tips dataset
tips = sns.load_dataset("tips")

# Display the first few rows of the dataset
print(tips.head())
```

### Other built-in datasets include "iris", "flights", "diamonds", and "penguins". You can load them in a similar manner:

```python
# Load the iris dataset
iris = sns.load_dataset("iris")

# Load the flights dataset
flights = sns.load_dataset("flights")
```

### Example: Visualizing the Iris Dataset
Let's create a pair plot using the iris dataset to visualize the relationships between different features of the dataset:

```python
# Load the iris dataset
iris = sns.load_dataset("iris")

# Create a pair plot
sns.pairplot(iris, hue="species")
plt.suptitle("Pair Plot of Iris Dataset", y=1.02)
plt.show()
```

## Themes and Aesthetic Styles
Seaborn comes with several built-in themes that make it easy to style your plots. These themes can be applied globally to all plots or to individual plots as needed. The available themes are:

- darkgrid: Default theme with a dark background grid.
- whitegrid: Light background with a grid.
- dark: Dark background without a grid.
- white: Light background without a grid.
- ticks: Light background with ticks on the axes.

### Applying a Theme
You can set a theme using the set_theme function. For example, to apply the whitegrid theme globally:

```python
# Set the theme
sns.set_theme(style="whitegrid")

# Create a box plot
sns.boxplot(data=tips, x="day", y="total_bill", hue="smoker")
plt.title("Box Plot of Total Bill by Day and Smoker")
plt.show()
```

## Customizing Aesthetic Styles
In addition to themes, Seaborn allows you to customize various aesthetic properties of your plots, such as color palettes, font sizes, and more.

### Color Palettes
Seaborn provides several built-in color palettes that can be used to enhance the appearance of your plots. You can set a color palette using the set_palette function:

```python
# Set the color palette
sns.set_palette("pastel")

# Create a bar plot
sns.barplot(data=tips, x="day", y="total_bill", hue="sex")
plt.title("Bar Plot of Total Bill by Day and Sex")
plt.show()
```

### Font Sizes
You can control the font sizes of various plot elements using the set_context function:

```python
# Set the context to "talk"
sns.set_context("talk")

# Create a line plot
sns.lineplot(data=flights, x="year", y="passengers", hue="month")
plt.title("Line Plot of Passengers Over Time")
plt.show()
```

## Example: Combining Themes and Custom Styles
Let's create a plot that combines a theme, a custom color palette, and adjusted font sizes:

```python
# Load the penguins dataset
penguins = sns.load_dataset("penguins")

# Set the theme and color palette
sns.set_theme(style="ticks", palette="deep")
sns.set_context("notebook", font_scale=1.2)

# Create a scatter plot
sns.scatterplot(data=penguins, x="bill_length_mm", y="bill_depth_mm", hue="species", style="species")
plt.title("Scatter Plot of Penguin Bill Dimensions")
plt.show()
```

In this example, we used the ticks theme, the deep color palette, and set the context to "notebook" with a slightly larger font scale. This combination results in a clean and visually appealing plot.

Conclusion
Seaborn's built-in datasets and themes provide powerful tools for creating attractive and informative visualizations with minimal effort. By leveraging these features, you can quickly create plots that are both visually appealing and effective at conveying your data's insights. Experiment with different themes, color palettes, and context settings to find the style that best suits your needs.
