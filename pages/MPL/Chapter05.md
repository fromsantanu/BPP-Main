# Styling and Themes
Matplotlib offers a variety of ways to style your plots to make them more visually appealing and consistent with the overall design of your project. This chapter will cover using built-in styles, customizing styles and themes, and working with color maps.

## Using Built-in Styles
Matplotlib comes with several built-in styles that can be applied to your plots to give them a consistent look and feel. You can see the available styles by using plt.style.available.

```python
import matplotlib.pyplot as plt

# List available styles
print(plt.style.available)
```

## Applying a Built-in Style
You can apply a style to your plots using plt.style.use.

```python
import matplotlib.pyplot as plt
import numpy as np

# Data for plotting
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Applying a built-in style
plt.style.use('ggplot')

# Creating the plot
plt.plot(x, y)
plt.title("Plot with ggplot Style")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")

# Display the plot
plt.show()
```

## Customizing Styles and Themes

### Creating Custom Styles
You can create your own style by modifying parameters in a dictionary and applying it using plt.rc.

```python
import matplotlib.pyplot as plt
import numpy as np

# Data for plotting
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Customizing styles
custom_style = {
    'axes.facecolor': 'lightgray',
    'axes.edgecolor': 'black',
    'axes.grid': True,
    'grid.alpha': 0.5,
    'grid.color': 'white',
    'grid.linestyle': '--',
    'lines.linewidth': 2,
    'lines.color': 'blue'
}

# Applying custom styles
plt.rcParams.update(custom_style)

# Creating the plot
plt.plot(x, y)
plt.title("Plot with Custom Style")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")

# Display the plot
plt.show()
```

### Using Context Managers for Temporary Styles
You can use context managers to temporarily apply a style for a specific plot or block of code.

```python
import matplotlib.pyplot as plt
import numpy as np

# Data for plotting
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Creating the plot with a temporary style
with plt.style.context('seaborn-dark'):
    plt.plot(x, y)
    plt.title("Plot with Temporary seaborn-dark Style")
    plt.xlabel("X-axis")
    plt.ylabel("Y-axis")
    plt.show()

# Creating the plot with default style
plt.plot(x, y)
plt.title("Plot with Default Style")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")
plt.show()
```

## Working with Color Maps
Color maps are useful for representing data in plots, especially for heatmaps, contour plots, and other visualizations that require a range of colors.

### Using Built-in Color Maps
Matplotlib comes with a variety of built-in color maps that can be applied to your plots.

```python
import matplotlib.pyplot as plt
import numpy as np

# Data for plotting
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Creating the plot with a color map
plt.scatter(x, y, c=y, cmap='viridis')
plt.title("Plot with Viridis Color Map")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")
plt.colorbar(label='Value')

# Display the plot
plt.show()
```

### Creating Custom Color Maps
You can create your own color maps using LinearSegmentedColormap.

```python
import matplotlib.pyplot as plt
import numpy as np
from matplotlib.colors import LinearSegmentedColormap

# Data for plotting
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Defining custom color map
colors = [(0, 'blue'), (0.5, 'white'), (1, 'red')]
custom_cmap = LinearSegmentedColormap.from_list('custom_cmap', colors)

# Creating the plot with custom color map
plt.scatter(x, y, c=y, cmap=custom_cmap)
plt.title("Plot with Custom Color Map")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")
plt.colorbar(label='Value')

# Display the plot
plt.show()
```

## Applying Color Maps to Different Plot Types
Color maps can be applied to various plot types, including heatmaps and contour plots.

### Heatmap Example

```python
import matplotlib.pyplot as plt
import numpy as np

# Generating random data for heatmap
data = np.random.rand(10, 10)

# Creating the heatmap
plt.imshow(data, cmap='hot', interpolation='nearest')
plt.title("Heatmap with Hot Color Map")
plt.colorbar(label='Value')

# Display the plot
plt.show()
```

### Contour Plot Example

```python
import matplotlib.pyplot as plt
import numpy as np

# Generating data for contour plot
x = np.linspace(-5, 5, 100)
y = np.linspace(-5, 5, 100)
X, Y = np.meshgrid(x, y)
Z = np.sin(np.sqrt(X**2 + Y**2))

# Creating the contour plot
plt.contourf(X, Y, Z, cmap='plasma')
plt.title("Contour Plot with Plasma Color Map")
plt.colorbar(label='Value')

# Display the plot
plt.show()
```

In this chapter, we have explored how to style and theme your plots in Matplotlib. We covered using built-in styles, customizing styles and themes, and working with color maps. These tools will help you create visually appealing and consistent visualizations for your data analysis projects.
