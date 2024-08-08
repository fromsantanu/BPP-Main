# 3D Plotting with Matplotlib
Matplotlib provides tools for 3D plotting through the mpl_toolkits.mplot3d module. This chapter will introduce 3D plotting, covering how to create 3D line, scatter, and surface plots, and how to customize 3D plots.

## Introduction to mpl_toolkits.mplot3d
The mpl_toolkits.mplot3d module provides the Axes3D class, which allows for the creation of 3D plots. To use this module, you need to import it and create a 3D axes instance.

```python
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
import numpy as np

# Creating a 3D plot
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')

# Data for plotting
x = np.linspace(-5, 5, 100)
y = np.linspace(-5, 5, 100)
X, Y = np.meshgrid(x, y)
Z = np.sin(np.sqrt(X**2 + Y**2))

# Plotting a 3D surface
ax.plot_surface(X, Y, Z)

# Adding title and labels
ax.set_title("3D Surface Plot")
ax.set_xlabel("X-axis")
ax.set_ylabel("Y-axis")
ax.set_zlabel("Z-axis")

# Display the plot
plt.show()
```

## 3D Line, Scatter, and Surface Plots

### 3D Line Plot
A 3D line plot is used to visualize data points connected by lines in three-dimensional space.

```python
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
import numpy as np

# Data for plotting
t = np.linspace(0, 2*np.pi, 100)
x = np.sin(t)
y = np.cos(t)
z = t

# Creating the plot
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
ax.plot(x, y, z)

# Adding title and labels
ax.set_title("3D Line Plot")
ax.set_xlabel("X-axis")
ax.set_ylabel("Y-axis")
ax.set_zlabel("Z-axis")

# Display the plot
plt.show()
```

### 3D Scatter Plot
A 3D scatter plot is used to visualize individual data points in three-dimensional space.

```python
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
import numpy as np

# Data for plotting
x = np.random.standard_normal(100)
y = np.random.standard_normal(100)
z = np.random.standard_normal(100)

# Creating the plot
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
ax.scatter(x, y, z)

# Adding title and labels
ax.set_title("3D Scatter Plot")
ax.set_xlabel("X-axis")
ax.set_ylabel("Y-axis")
ax.set_zlabel("Z-axis")

# Display the plot
plt.show()
```

### 3D Surface Plot
A 3D surface plot is used to visualize a three-dimensional surface that fits the data points.

```python
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
import numpy as np

# Data for plotting
x = np.linspace(-5, 5, 100)
y = np.linspace(-5, 5, 100)
X, Y = np.meshgrid(x, y)
Z = np.sin(np.sqrt(X**2 + Y**2))

# Creating the plot
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
ax.plot_surface(X, Y, Z, cmap='viridis')

# Adding title and labels
ax.set_title("3D Surface Plot")
ax.set_xlabel("X-axis")
ax.set_ylabel("Y-axis")
ax.set_zlabel("Z-axis")

# Display the plot
plt.show()
```

## Customizing 3D Plots

### Customizing Colors and Styles
You can customize the colors and styles of 3D plots to make them more informative and visually appealing.

```python
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
import numpy as np

# Data for plotting
x = np.linspace(-5, 5, 100)
y = np.linspace(-5, 5, 100)
X, Y = np.meshgrid(x, y)
Z = np.sin(np.sqrt(X**2 + Y**2))

# Creating the plot
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
surf = ax.plot_surface(X, Y, Z, cmap='coolwarm', edgecolor='none')

# Adding title and labels
ax.set_title("Customized 3D Surface Plot")
ax.set_xlabel("X-axis")
ax.set_ylabel("Y-axis")
ax.set_zlabel("Z-axis")

# Adding a color bar
fig.colorbar(surf, shrink=0.5, aspect=5)

# Display the plot
plt.show()
```

### Changing View Angles
You can change the view angles to get different perspectives of the 3D plot.

```python
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
import numpy as np

# Data for plotting
x = np.linspace(-5, 5, 100)
y = np.linspace(-5, 5, 100)
X, Y = np.meshgrid(x, y)
Z = np.sin(np.sqrt(X**2 + Y**2))

# Creating the plot
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
ax.plot_surface(X, Y, Z, cmap='viridis')

# Changing view angles
ax.view_init(elev=30, azim=60)

# Adding title and labels
ax.set_title("3D Surface Plot with Changed View Angles")
ax.set_xlabel("X-axis")
ax.set_ylabel("Y-axis")
ax.set_zlabel("Z-axis")

# Display the plot
plt.show()
```

### Adding Annotations
You can add annotations to highlight specific points or areas in the 3D plot.

```python
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D
import numpy as np

# Data for plotting
t = np.linspace(0, 2*np.pi, 100)
x = np.sin(t)
y = np.cos(t)
z = t

# Creating the plot
fig = plt.figure()
ax = fig.add_subplot(111, projection='3d')
ax.plot(x, y, z)

# Adding annotations
ax.text(0, 0, 0, "Origin", color='red')
ax.text(1, 0, 2*np.pi, "End", color='blue')

# Adding title and labels
ax.set_title("3D Line Plot with Annotations")
ax.set_xlabel("X-axis")
ax.set_ylabel("Y-axis")
ax.set_zlabel("Z-axis")

# Display the plot
plt.show()
```

In this chapter, we have explored 3D plotting with Matplotlib. We covered the basics of the mpl_toolkits.mplot3d module, creating 3D line, scatter, and surface plots, and customizing 3D plots with colors, styles, view angles, and annotations. These tools will help you create informative and visually appealing 3D visualizations for your data analysis projects.
