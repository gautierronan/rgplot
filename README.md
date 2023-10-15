# rgstyle
A custom matplotlib style to generate nice-looking matplotlib figures, with just a single line `plt.style.use('rgstyle')`.

## Example
Reproduce the plot below with the following few lines of Python.
```python
import matplotlib.pyplot as plt
import numpy as np

# use custom style
plt.style.use('rgstyle')

# sample data
x = np.linspace(0, 2*np.pi, 100)
y = (np.sin(x) * np.exp(-0.5 * x)).repeat(5).reshape(-1, 5) * np.linspace(0.5, 1.5, 5)

# make plot
plt.plot(x, y)
plt.xlabel("Time")
plt.ylabel("Damped sine")
plt.title("Sample plot with `rgstyle`")
plt.legend((r"$r = 0$", r"$r = 1$", r"$r = 2$", r"$r = 3$", r"$r = 4$"))
plt.show()
```
![sampleplot_rgstyle](https://github.com/gautierronan/rgstyle/assets/25346881/782dc355-f50e-4d61-aaec-2766215cbb6e)

## Installation
```
mkdir -p "$(python -c "import matplotlib; print(matplotlib.get_configdir())")/stylelib"
wget -P "$(python -c "import matplotlib; print(matplotlib.get_configdir())")/stylelib" https://raw.githubusercontent.com/gautierronan/rgstyle/main/rgstyle.mplstyle
```
Alternatively, you can download `rgstyle.mplstyle` and place it in your matplotlib style folder. You can find your matplotlib folder by running `matplotlib.get_configdir()` in a Python environment, with `matplotlib` imported. By default, the matplotlib folder is `~\.matplotlib\stylelib\`. 
