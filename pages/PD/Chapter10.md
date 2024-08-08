# Chapter 10: Data Visualization with Pandas

## 10.1 Plotting Basics
Pandas integrates with Matplotlib to provide easy plotting capabilities directly from DataFrame and Series objects.

### Creating a sample DataFrame:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# Creating a sample DataFrame
data = {
    'Month': ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
    'Sales': [200, 210, 180, 250, 300, 320, 310, 400, 420, 390, 380, 450]
}
df = pd.DataFrame(data)
```

### Basic plotting:

```python
# Plotting the data
df.plot(x='Month', y='Sales', kind='line')
plt.show()
```

## 10.2 Line Plots, Bar Plots, Histograms, Box Plots

### Line plots:

```python
# Line plot
df.plot(x='Month', y='Sales', kind='line', title='Monthly Sales')
plt.xlabel('Month')
plt.ylabel('Sales')
plt.show()
```

### Bar plots:

```python
# Bar plot
df.plot(x='Month', y='Sales', kind='bar', title='Monthly Sales')
plt.xlabel('Month')
plt.ylabel('Sales')
plt.show()
```

### Histograms:

```python
# Creating a sample DataFrame for histogram
data_hist = {
    'Score': np.random.normal(70, 10, 100)
}
df_hist = pd.DataFrame(data_hist)

# Histogram
df_hist.plot(kind='hist', bins=10, title='Score Distribution')
plt.xlabel('Score')
plt.show()
```

### Box plots:

```python
# Creating a sample DataFrame for box plot
data_box = {
    'Math': np.random.randint(50, 100, 100),
    'Science': np.random.randint(50, 100, 100),
    'English': np.random.randint(50, 100, 100)
}
df_box = pd.DataFrame(data_box)

# Box plot
df_box.plot(kind='box', title='Score Distribution by Subject')
plt.show()
```

## 10.3 Customizing Plots

### Customizing plot appearance:

```python
# Customizing line plot appearance
df.plot(x='Month', y='Sales', kind='line', title='Monthly Sales', color='red', linestyle='--', marker='o')
plt.xlabel('Month')
plt.ylabel('Sales')
plt.grid(True)
plt.show()
```

### Adding multiple plots:

```python
# Creating additional data for multiple plots
df['Profit'] = [50, 55, 45, 60, 80, 90, 85, 110, 120, 115, 110, 140]

# Plotting Sales and Profit on the same graph
ax = df.plot(x='Month', y='Sales', kind='line', title='Monthly Sales and Profit', color='blue', marker='o')
df.plot(x='Month', y='Profit', kind='line', color='green', marker='x', ax=ax)
plt.xlabel('Month')
plt.ylabel('Amount')
plt.show()
```

### Subplots:

```python
# Creating subplots
fig, axes = plt.subplots(nrows=2, ncols=1, figsize=(8, 6))

df.plot(x='Month', y='Sales', kind='line', ax=axes[0], title='Monthly Sales', color='blue', marker='o')
df.plot(x='Month', y='Profit', kind='line', ax=axes[1], title='Monthly Profit', color='green', marker='x')

axes[0].set_xlabel('Month')
axes[0].set_ylabel('Sales')
axes[0].grid(True)

axes[1].set_xlabel('Month')
axes[1].set_ylabel('Profit')
axes[1].grid(True)

plt.tight_layout()
plt.show()
```

### Adding annotations:

```python
# Adding annotations to a plot
ax = df.plot(x='Month', y='Sales', kind='line', title='Monthly Sales', color='blue', marker='o')
for i, txt in enumerate(df['Sales']):
    ax.annotate(txt, (df['Month'][i], df['Sales'][i]), textcoords="offset points", xytext=(0,10), ha='center')

plt.xlabel('Month')
plt.ylabel('Sales')
plt.show()
```

By the end of this chapter, you should be able to create and customize various types of plots using Pandas, enabling effective visualization of your data.
