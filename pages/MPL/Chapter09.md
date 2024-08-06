Saving and Exporting Plots
Saving and exporting plots is an essential part of data visualization, allowing you to share your work or include it in reports and presentations. This chapter will cover saving figures in different formats, adjusting resolution and size, and embedding Matplotlib in applications.

Saving Figures in Different Formats
Matplotlib allows you to save figures in various formats, such as PNG, PDF, SVG, and more, using the savefig function.

Saving as PNG
python
Copy code
import matplotlib.pyplot as plt
import numpy as np

# Data for plotting
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Creating the plot
plt.plot(x, y)

# Adding title and labels
plt.title("Sine Wave")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")

# Saving the figure as a PNG file
plt.savefig("sine_wave.png")

# Display the plot
plt.show()
Saving as PDF
python
Copy code
import matplotlib.pyplot as plt
import numpy as np

# Data for plotting
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Creating the plot
plt.plot(x, y)

# Adding title and labels
plt.title("Sine Wave")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")

# Saving the figure as a PDF file
plt.savefig("sine_wave.pdf")

# Display the plot
plt.show()
Saving as SVG
python
Copy code
import matplotlib.pyplot as plt
import numpy as np

# Data for plotting
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Creating the plot
plt.plot(x, y)

# Adding title and labels
plt.title("Sine Wave")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")

# Saving the figure as an SVG file
plt.savefig("sine_wave.svg")

# Display the plot
plt.show()
Adjusting Resolution and Size
You can adjust the resolution and size of your figures to suit different requirements, such as high-resolution prints or web display.

Adjusting DPI (Dots Per Inch)
The DPI setting controls the resolution of the saved figure.

python
Copy code
import matplotlib.pyplot as plt
import numpy as np

# Data for plotting
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Creating the plot
plt.plot(x, y)

# Adding title and labels
plt.title("Sine Wave")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")

# Saving the figure with adjusted DPI
plt.savefig("sine_wave_high_dpi.png", dpi=300)

# Display the plot
plt.show()
Adjusting Figure Size
You can adjust the figure size using the figsize parameter in the figure function.

python
Copy code
import matplotlib.pyplot as plt
import numpy as np

# Data for plotting
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Creating the plot with adjusted figure size
plt.figure(figsize=(10, 6))
plt.plot(x, y)

# Adding title and labels
plt.title("Sine Wave")
plt.xlabel("X-axis")
plt.ylabel("Y-axis")

# Saving the figure with adjusted size
plt.savefig("sine_wave_large.png")

# Display the plot
plt.show()
Embedding Matplotlib in Applications
Matplotlib can be embedded in various applications, such as graphical user interfaces (GUIs), web applications, and more. Here, we will explore how to embed Matplotlib in a simple Tkinter application.

Embedding in Tkinter
Tkinter is a standard Python library for creating GUIs. You can embed Matplotlib plots in Tkinter applications using the FigureCanvasTkAgg class.

python
Copy code
import matplotlib.pyplot as plt
import numpy as np
from matplotlib.backends.backend_tkagg import FigureCanvasTkAgg
import tkinter as tk

# Data for plotting
x = np.linspace(0, 10, 100)
y = np.sin(x)

# Creating the Tkinter window
root = tk.Tk()
root.title("Matplotlib in Tkinter")

# Creating the Matplotlib figure
fig, ax = plt.subplots()
ax.plot(x, y)
ax.set_title("Sine Wave")
ax.set_xlabel("X-axis")
ax.set_ylabel("Y-axis")

# Embedding the figure in the Tkinter window
canvas = FigureCanvasTkAgg(fig, master=root)
canvas.draw()
canvas.get_tk_widget().pack(side=tk.TOP, fill=tk.BOTH, expand=1)

# Adding a quit button
button = tk.Button(master=root, text="Quit", command=root.quit)
button.pack(side=tk.BOTTOM)

# Running the Tkinter main loop
root.mainloop()
In this chapter, we have explored how to save and export plots in different formats, adjust the resolution and size of figures, and embed Matplotlib in applications. These techniques will help you share your visualizations effectively and integrate them into various applications.
