# Subplots and Layouts
Creating multiple plots in a single figure can help you compare different datasets or visualize different aspects of the same data. Matplotlib offers several ways to create subplots and custom layouts, making it a powerful tool for complex data visualization.

## Creating Subplots with subplot and subplots
### Using subplot
The subplot function allows you to create a grid of subplots within a single figure. The function takes three arguments: the number of rows, the number of columns, and the index of the subplot.

```python
import matplotlib.pyplot as plt
import numpy as np

# Data for plotting
x = np.linspace(0, 10, 100)
y1 = np.sin(x)
y2 = np.cos(x)

# Creating subplots
plt.figure(figsize=(10, 5))

plt.subplot(2, 1, 1)  # 2 rows, 1 column, 1st subplot
plt.plot(x, y1)
plt.title("Sine Wave")

plt.subplot(2, 1, 2)  # 2 rows, 1 column, 2nd subplot
plt.plot(x, y2)
plt.title("Cosine Wave")

# Adjusting layout
plt.tight_layout()
plt.show()
```

### Using subplots
The subplots function is more flexible and convenient for creating a grid of subplots. It returns a figure and an array of axes objects.

```python
import matplotlib.pyplot as plt
import numpy as np

# Data for plotting
x = np.linspace(0, 10, 100)
y1 = np.sin(x)
y2 = np.cos(x)

# Creating subplots
fig, axs = plt.subplots(2, 1, figsize=(10, 5))

# Plotting on the first subplot
axs[0].plot(x, y1)
axs[0].set_title("Sine Wave")

# Plotting on the second subplot
axs[1].plot(x, y2)
axs[1].set_title("Cosine Wave")

# Adjusting layout
plt.tight_layout()
plt.show()
```

## GridSpec and Custom Layouts

### Using GridSpec
GridSpec allows for more complex and custom subplot layouts than subplot and subplots.

```python
import matplotlib.pyplot as plt
import matplotlib.gridspec as gridspec
import numpy as np

# Data for plotting
x = np.linspace(0, 10, 100)
y1 = np.sin(x)
y2 = np.cos(x)
y3 = np.tan(x)

# Creating a GridSpec layout
fig = plt.figure(figsize=(10, 10))
gs = gridspec.GridSpec(3, 3)

# Creating subplots with GridSpec
ax1 = fig.add_subplot(gs[0, :])
ax2 = fig.add_subplot(gs[1, :-1])
ax3 = fig.add_subplot(gs[1:, -1])
ax4 = fig.add_subplot(gs[-1, 0])
ax5 = fig.add_subplot(gs[-1, -2])

# Plotting data
ax1.plot(x, y1)
ax1.set_title("Sine Wave")
ax2.plot(x, y2)
ax2.set_title("Cosine Wave")
ax3.plot(x, y3)
ax3.set_title("Tangent Wave")
ax4.plot(x, -y1)
ax4.set_title("Negative Sine Wave")
ax5.plot(x, -y2)
ax5.set_title("Negative Cosine Wave")

# Adjusting layout
plt.tight_layout()
plt.show()
```

## Sharing Axes
### Sharing Axes in Subplots
Sharing axes can be useful when you want to compare plots directly. You can share the x-axis, y-axis, or both.

```python
import matplotlib.pyplot as plt
import numpy as np

# Data for plotting
x = np.linspace(0, 10, 100)
y1 = np.sin(x)
y2 = np.cos(x)

# Creating subplots with shared axes
fig, (ax1, ax2) = plt.subplots(2, 1, sharex=True, figsize=(10, 5))

# Plotting data
ax1.plot(x, y1)
ax1.set_title("Sine Wave")

ax2.plot(x, y2)
ax2.set_title("Cosine Wave")
ax2.set_xlabel("X-axis")

# Adding common y-label
fig.text(0.04, 0.5, 'Y-axis', va='center', rotation='vertical')

# Adjusting layout
plt.tight_layout()
plt.show()
```

### Sharing Both Axes

```python
import matplotlib.pyplot as plt
import numpy as np

# Data for plotting
x = np.linspace(0, 10, 100)
y1 = np.sin(x)
y2 = np.cos(x)
y3 = np.tan(x)

# Creating subplots with shared axes
fig, axs = plt.subplots(2, 2, sharex=True, sharey=True, figsize=(10, 10))

# Plotting data
axs[0, 0].plot(x, y1)
axs[0, 0].set_title("Sine Wave")

axs[0, 1].plot(x, y2)
axs[0, 1].set_title("Cosine Wave")

axs[1, 0].plot(x, y3)
axs[1, 0].set_title("Tangent Wave")

axs[1, 1].plot(x, -y1)
axs[1, 1].set_title("Negative Sine Wave")

# Adding common x and y labels
fig.text(0.5, 0.04, 'X-axis', ha='center')
fig.text(0.04, 0.5, 'Y-axis', va='center', rotation='vertical')

# Adjusting layout
plt.tight_layout()
plt.show()
```

In this chapter, we have explored how to create and customize subplots and layouts in Matplotlib. We covered the use of subplot and subplots, GridSpec for custom layouts, and sharing axes between subplots. These techniques will help you create complex and informative visualizations for your data analysis needs.
