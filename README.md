# rgplot
A custom matplotlib style to generate nice-looking matplotlib figures, with just a single line `plt.style.use('rgplot')`.

## Example
Reproduce the right-side plot below with the following few lines of Python.
```python
import matplotlib.pyplot as plt
import numpy as np

# use custom style
plt.style.use('rgplot')

# sample data
x = np.linspace(0, 2*np.pi, 100)
y = (np.sin(x) * np.exp(-0.5 * x)).repeat(5).reshape(-1, 5) * np.linspace(0.5, 1.5, 5)

# make plot
plt.plot(x, y)
plt.xlabel("Time")
plt.ylabel("Damped sine")
plt.legend((r"$r = 0$", r"$r = 1$", r"$r = 2$", r"$r = 3$", r"$r = 4$"))
plt.show()
```
![sampleplot_comparison-01](https://github.com/gautierronan/rgplot/assets/25346881/e8b7c162-29b8-4da9-88a5-77657c5f5348)

## Installation
```
mkdir -p "$(python -c "import matplotlib; print(matplotlib.get_configdir())")/stylelib"
wget -P "$(python -c "import matplotlib; print(matplotlib.get_configdir())")/stylelib" https://raw.githubusercontent.com/gautierronan/rgplot/main/rgplot.mplstyle
```
Alternatively, you can download `rgplot.mplstyle` and place it in your matplotlib style folder. You can find your matplotlib folder by running `matplotlib.get_configdir()` in a Python environment, with `matplotlib` imported. By default, the matplotlib folder is `~\.matplotlib\stylelib\`. 
