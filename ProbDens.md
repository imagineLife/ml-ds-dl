# Probability Density Fns
In continuous data
**Normal Distribution**
the probability of a specific value appearing is infinitely small.

A Probability Distribution function gives the probability of a data point falling within some given range of a given value.
**see the "Normal Distribution" img**

In Discrete data
**Probability Mass Function**


## Distribution types
### Uniform Distribution
A flat, contant probability curve of values showing up in a data-set.
Building in python
```
%matplotlib inline

import numpy as np
import matplotlib.pyplot as plt

values = np.random.uniform(-10.0, 10.0, 100000)
plt.hist(values, 50)
plt.show()
```
**notice np.random.uniform()**
- builds a flat dist

### Normal / Gaussian Distribution
build in python
```
from scipy.stats import norm
import matplotlib.pyplot as plt

x = np.arange(-3, 3, 0.001)
plt.plot(x, norm.pdf(x))
```
- import the NORM package from scipy
- create a range of x-values
	- between -3 && 3, increment of .0001 between them
- plot the x axis
- y-axis will be normal fn (norm.pdf(x)) on the x values
	- pdf stands for Probability Density Function

Generating Some Random numbers w. a normal dist
- **mu** is the desired mean
- **sigma** is the standard dev desired of the data
```
import numpy as np
import matplotlib.pyplot as plt

mu = 5.0
sigma = 2.0
values = np.random.normal(mu, sigma, 10000)
plt.hist(values, 50)
plt.show()
```

### Exponential PDF / "Power Law"
things fall off exponentially as they increase
```
from scipy.stats import expon
import matplotlib.pyplot as plt

x = np.arange(0, 10, 0.001)
plt.plot(x, expon.pdf(x))
```
- expon.pdf is an exponential fn in scipy 

## Probability Mass Functions
### Binomial Probability Mass Fn
- dealing w. discrete data sets, not continuous
```
from scipy.stats import binom
import matplotlib.pyplot as plt

n, p = 10, 0.5
x = np.arange(0, 10, 0.001)
plt.plot(x, binom.pmf(x, n, p))
```

### Poisson Prob. Mass Fn
if we have info re the avg number of things that happen in some gibven time period, can help predict getting other values on a given day
i.e
- a web page
- gets 500 hits per day
- can use the poisson to est. the probability of seeing some other value
- ...whats the prob. of seeing 550 visitors on a given day?!
```
from scipy.stats import poisson
import matplotlib.pyplot as plt

mu = 500
x = np.arange(400, 600, 0.5)
plt.plot(x, poisson.pmf(x, mu))
```
