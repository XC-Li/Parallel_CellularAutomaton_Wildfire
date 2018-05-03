# Wildfire simulation using paralleled cellular automaton

## Environment Specification
In order to achieve best compatibility, this program only needs very basic prerequisite.
1. Openmpi/3.0.0
2. Python/2.7.11 (and mpi4py package)

However, to generate a better visualization, this program needs additional packages.
1. numpy
2. matplotlib
If the program failed to import these two packages, then it will automatically run in pure text mode.

## Usage
### Easiest place to change
This program is carefully designed, so the places you can change is very few.
The easiest part to change is surrounded by `-----Quick Change-----`.
You can simply change:

|Variable Name|Acceptable Value|Purpose|
|-----|-----|-----|
|n_row_total|any positive integer| the total row of the grid|
|n_col|any positive integer| the total column of the grid|
|generation| any positive integer| the total number of iterations|
|p_continue_burn|between 0 and 1|the possibility one cell continues to burn in next time step|
|wind|True or False|Switch for wind factor in the model (True for on, False for off)|
|vegetation|True or False|Switch for vegetation factor in the model (True for on, False for off)|
|density|True or False|Switch for vegetation density factor in the model(True for on, False for off)|
|altitude|True or False|Switch for altitude factor in the model(True for on, False for off)|

Or you can do some custom changes on the environment initial functions:

|Function Name|Purpose|Output|
|----|----|----|
|thetas (a list)|the angle of wind and direction of fire spread| 3x3 list|
|init_vegation|the matrix for vegetation type|n_colxn_row list|
|init_density|the matrix for vegetation density|n_colxn_row list|
|init_altitude|the matrix for altitude|n_colxn_row list|
|init_forest|the matrix for initial forest condition|n_colxn_row list|

**Please don't change anything below the line `Do not change anything below this line`**

### Run the code:
After loading the module, you can use `mpirun -n [n] python Parallel_Wild_Fire.py` to run this code.
You can specify the number of workers in `n` if you have multiple CPU.

## Model and Implimentation
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"></script>
居中格式: $$xxx$$
$$x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$$
## Parallel Version
