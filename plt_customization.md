# Uniform Customization of Matplotlib Plots

If you want to use a uniform style for plots, I have modified a `.mplstyle` file that you can use to automatically format plots.

## What changes did I want
1. Uniform dpi for saved figures (275).
2. Using colorblind friendlier pallets.
3. Dark and large text.
4. Light grid lines.


## To use in a jupyter notebook
To use this in a Jupyter Notebook, run the following code:

```
import matplotlib
matplotlib.use
import matplotlib.pyplot as plt
plt.style.use('nathan.mplstyle')
```