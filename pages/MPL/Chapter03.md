# Advanced Plot Types in Matplotlib
Matplotlib offers a variety of advanced plot types for in-depth data analysis. This chapter will cover histograms and density plots, pie and donut charts, and boxplots and violin plots.

## Histograms and Density Plots

### Histograms
Histograms are used to represent the distribution of a dataset by dividing it into bins and counting the number of data points in each bin.

```python
import matplotlib.pyplot as plt
import numpy as np

# Generating random data
data = np.random.randn(1000)

# Creating the histogram
plt.hist(data, bins=30, edgecolor='black')

# Adding title and labels
plt.title("Histogram")
plt.xlabel("Value")
plt.ylabel("Frequency")

# Display the plot
plt.show()
```

### Density Plots
Density plots, or kernel density estimates (KDE), represent the data distribution as a continuous probability density curve.

```python
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np

# Generating random data
data = np.random.randn(1000)

# Creating the density plot
sns.kdeplot(data, shade=True)

# Adding title and labels
plt.title("Density Plot")
plt.xlabel("Value")
plt.ylabel("Density")

# Display the plot
plt.show()
```

## Pie and Donut Charts

### Pie Charts
Pie charts show the proportions of a whole by dividing it into slices.

```python
import matplotlib.pyplot as plt

# Data for plotting
labels = ['A', 'B', 'C', 'D']
sizes = [15, 30, 45, 10]
colors = ['gold', 'yellowgreen', 'lightcoral', 'lightskyblue']
explode = (0.1, 0, 0, 0)  # explode the first slice

# Creating the pie chart
plt.pie(sizes, explode=explode, labels=labels, colors=colors, autopct='%1.1f%%', shadow=True, startangle=140)

# Adding title
plt.title("Pie Chart")

# Display the plot
plt.axis('equal')
plt.show()
```

### Donut Charts
Donut charts are similar to pie charts but have a central hole, making them look like a donut.

```python
import matplotlib.pyplot as plt

# Data for plotting
labels = ['A', 'B', 'C', 'D']
sizes = [15, 30, 45, 10]
colors = ['gold', 'yellowgreen', 'lightcoral', 'lightskyblue']
explode = (0.1, 0, 0, 0)  # explode the first slice

# Creating the donut chart
plt.pie(sizes, explode=explode, labels=labels, colors=colors, autopct='%1.1f%%', shadow=True, startangle=140)
centre_circle = plt.Circle((0,0),0.70,fc='white')
fig = plt.gcf()
fig.gca().add_artist(centre_circle)

# Adding title
plt.title("Donut Chart")

# Display the plot
plt.axis('equal')
plt.show()
```

## Boxplots and Violin Plots

### Boxplots
Boxplots are used to display the distribution of a dataset based on five summary statistics: minimum, first quartile (Q1), median, third quartile (Q3), and maximum.

```python
import matplotlib.pyplot as plt
import numpy as np

# Generating random data
data = [np.random.normal(0, std, 100) for std in range(1, 4)]

# Creating the boxplot
plt.boxplot(data, vert=True, patch_artist=True)

# Adding title and labels
plt.title("Boxplot")
plt.xlabel("Dataset")
plt.ylabel("Value")

# Display the plot
plt.show()
```

### Violin Plots
Violin plots combine the features of boxplots and density plots. They show the distribution of the data across different categories.

```python
import matplotlib.pyplot as plt
import seaborn as sns
import numpy as np

# Generating random data
data = [np.random.normal(0, std, 100) for std in range(1, 4)]

# Creating the violin plot
sns.violinplot(data=data)

# Adding title and labels
plt.title("Violin Plot")
plt.xlabel("Dataset")
plt.ylabel("Value")

# Display the plot
plt.show()
```

In this chapter, we explored various advanced plot types in Matplotlib, including histograms, density plots, pie and donut charts, and boxplots and violin plots. These plot types can help you perform more detailed and nuanced data analysis.
