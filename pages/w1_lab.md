As in each week, we will finish with a lab session, were you can work at your
own speed on exercises for material during the week.

This is where we will give you the notebooks for you to submit each week.

Please remember — our purpose for asking you submit these notebooks is to make
sure that you are keeping up with the material, because coding can get very
tough if you start to fall behind.  But, we will give you 40% of the marks
whatever notebook you submit, and the rest of the marks depending on whether
your answers in the notebook are right.

You can work in pairs for the labs, and in fact, we recommend that you do.
There is some evidence that working in pairs can improve learning for
programming.

Notes:

* [Teach yourself programming in 10 years](https://www.norvig.com/21-days.html)
* [A sampling
  problem](https://lisds.github.io/textbook/code-basics/sampling_problem.html)
* [A simpler
  problem](https://lisds.github.io/textbook/code-basics/three_girls.html)

I asked you to fill in and submit the [Rounding exercise](https://ds.lis.2i2c.cloud/hub/user-redirect/git-pull?repo=https%3A//github.com/lisds/rounding&subPath=rounding.ipynb).

The notebook from class on the three girls problem had the following solution.
Copy / paste into a new notebook to try it:


```python
import numpy as np

# Make a random number generator
rng = np.random.default_rng()

# Make an array with 10000 zeros.
results = np.zeros(10000)
# Repeat 10000 times.
for i in np.arange(10000):
    # Select randomly from 0 and 1 4 times to make boy / girl choice.
    family = rng.integers(0, 2, size=4)
    # Count the number of girls by adding up all the elements.
    n_girls = np.sum(family)
    # Store the result in the array at the current position.
    results[i] = n_girls

# Make True for all counts equal to 3, False otherwise.
are_three = results == 3
# Show the proportion of counts that were equal to 3.
np.count_nonzero(are_three) / 10000
