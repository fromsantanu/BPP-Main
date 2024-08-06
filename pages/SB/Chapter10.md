Integration with Matplotlib
Seaborn is built on top of Matplotlib, making it easy to combine the strengths of both libraries to create powerful and customized visualizations. This chapter explores how to integrate Seaborn and Matplotlib, customize Seaborn plots with Matplotlib, create complex visualizations, and provides practical applications and case studies.

Combining Seaborn and Matplotlib
Seaborn plots can be easily combined with Matplotlib's functionalities to enhance and customize visualizations.

Basic Integration
python
Copy code
import seaborn as sns
import matplotlib.pyplot as plt

# Load the tips dataset
tips = sns.load_dataset("tips")

# Create a Seaborn plot
sns.histplot(data=tips, x="total_bill", kde=True)

# Customize with Matplotlib
plt.title("Histogram of Total Bill with KDE")
plt.xlabel("Total Bill ($)")
plt.ylabel("Frequency")
plt.show()
Customizing Seaborn Plots with Matplotlib
You can use Matplotlib's functions to customize Seaborn plots, such as adding annotations, changing figure sizes, and modifying axis properties.

Adding Annotations
python
Copy code
# Create a Seaborn scatter plot
sns.scatterplot(data=tips, x="total_bill", y="tip", hue="time")

# Customize with Matplotlib
plt.title("Scatter Plot of Total Bill vs Tip")
plt.xlabel("Total Bill ($)")
plt.ylabel("Tip ($)")
plt.annotate("Highest Tip", xy=(50, 10), xytext=(40, 12),
             arrowprops=dict(facecolor='black', arrowstyle="->"))
plt.show()
Changing Figure Size
python
Copy code
# Create a Seaborn box plot
plt.figure(figsize=(10, 6))
sns.boxplot(data=tips, x="day", y="total_bill", hue="smoker")
plt.title("Box Plot of Total Bill by Day and Smoker")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill ($)")
plt.show()
Modifying Axis Properties
python
Copy code
# Create a Seaborn violin plot
sns.violinplot(data=tips, x="day", y="total_bill", hue="sex", split=True)

# Customize with Matplotlib
plt.title("Violin Plot of Total Bill by Day and Sex")
plt.xlabel("Day of the Week")
plt.ylabel("Total Bill ($)")
plt.xticks(rotation=45)
plt.grid(True)
plt.show()
Creating Complex Visualizations
Combining Seaborn and Matplotlib allows you to create complex and detailed visualizations that are highly customizable.

Complex Example: Multi-Faceted Plot with Annotations
python
Copy code
# Create a FacetGrid with customized legends, titles, and annotations
g = sns.FacetGrid(tips, col="time", hue="sex", height=5, aspect=1.2)
g.map(sns.scatterplot, "total_bill", "tip", alpha=0.7)
g.add_legend(title="Sex")
g.set_titles("{col_name} Time")
g.set_axis_labels("Total Bill ($)", "Tip ($)")
g.fig.suptitle("Customized FacetGrid of Total Bill vs Tip by Time and Sex", y=1.02)

# Add annotations using Matplotlib
axes = g.axes.flatten()
axes[0].annotate("High Tip", xy=(50, 10), xytext=(40, 12),
                 arrowprops=dict(facecolor='black', arrowstyle="->"))

plt.show()
Practical Applications and Case Studies
Case Study 1: Analyzing Flight Data
python
Copy code
# Load the flights dataset
flights = sns.load_dataset("flights")

# Pivot the dataset to create a matrix format
flights_pivot = flights.pivot("month", "year", "passengers")

# Create a heatmap with Seaborn
plt.figure(figsize=(12, 8))
sns.heatmap(data=flights_pivot, annot=True, fmt="d", cmap="YlGnBu")

# Customize with Matplotlib
plt.title("Heatmap of Passengers Over Time")
plt.xlabel("Year")
plt.ylabel("Month")
plt.show()
Case Study 2: Visualizing Iris Dataset Relationships
python
Copy code
# Load the iris dataset
iris = sns.load_dataset("iris")

# Create a pair plot with regression lines
g = sns.pairplot(iris, hue="species", kind="reg")

# Customize with Matplotlib
g.fig.suptitle("Pair Plot of Iris Dataset with Regression Lines", y=1.02)
for ax in g.axes.flatten():
    ax.set_xlabel(ax.get_xlabel(), fontsize=12)
    ax.set_ylabel(ax.get_ylabel(), fontsize=12)
    ax.set_title(ax.get_title(), fontsize=14)

plt.show()
Case Study 3: Custom Dashboard for Tips Data
python
Copy code
# Create a figure with subplots
fig, ax = plt.subplots(2, 2, figsize=(14, 12))

# Subplot 1: Histogram of Total Bill
sns.histplot(data=tips, x="total_bill", kde=True, ax=ax[0, 0])
ax[0, 0].set_title("Histogram of Total Bill")
ax[0, 0].set_xlabel("Total Bill ($)")
ax[0, 0].set_ylabel("Frequency")

# Subplot 2: Box Plot of Total Bill by Day and Smoker
sns.boxplot(data=tips, x="day", y="total_bill", hue="smoker", ax=ax[0, 1])
ax[0, 1].set_title("Box Plot of Total Bill by Day and Smoker")
ax[0, 1].set_xlabel("Day of the Week")
ax[0, 1].set_ylabel("Total Bill ($)")

# Subplot 3: Violin Plot of Total Bill by Day and Sex
sns.violinplot(data=tips, x="day", y="total_bill", hue="sex", split=True, ax=ax[1, 0])
ax[1, 0].set_title("Violin Plot of Total Bill by Day and Sex")
ax[1, 0].set_xlabel("Day of the Week")
ax[1, 0].set_ylabel("Total Bill ($)")

# Subplot 4: Scatter Plot of Total Bill vs Tip
sns.scatterplot(data=tips, x="total_bill", y="tip", hue="time", style="sex", ax=ax[1, 1])
ax[1, 1].set_title("Scatter Plot of Total Bill vs Tip")
ax[1, 1].set_xlabel("Total Bill ($)")
ax[1, 1].set_ylabel("Tip ($)")

# Adjust layout
plt.tight_layout()
plt.suptitle("Custom Dashboard for Tips Data", y=1.02)
plt.show()
Conclusion
Integrating Seaborn with Matplotlib provides powerful tools for creating highly customizable and complex visualizations. By combining the strengths of both libraries, you can create detailed, informative, and visually appealing plots for various data analysis tasks. This chapter covered the basics of integration, customization techniques, and practical applications through case studies, demonstrating the flexibility and power of Seaborn and Matplotlib together.
