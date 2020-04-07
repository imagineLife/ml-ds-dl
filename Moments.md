# Moments
- Quantitative measures of the shape of a probability density fn
- **FIRST** moment is the mean
- **SECOND** moment is the variance
- **THIRD** moment is called skew
	- how lopsided a distribution is...
		- if a longer tail or lesser slope curve is on the left of the mean, that is a **negative skew**
		- a longer tail on the right is a **positive skew**
- **FOURTH** is the kurtosis
	- kurtosis is how...
		- "thick" is the tail
		- "sharp" is the peak
			- higher the peak, the higher the kurtosis

## Calculating Moments in Python
- create a normal dist of data
```
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt

vals = np.random.normal(0, 0.5, 10000)

plt.hist(vals, 50)
plt.show()
```

- **FIRST MOMENT**: the mean
```np.mean(vals)```, here .0056...
- **SECOND MOMENT**: the variance
```np.var(vals)```, here, .2468....
- **THIRD MOMENT**: the skew
```
import scipy.stats as sp
sp.skew(vals)
```
here, -.0238...

-**FOURTH MOMENT**: kurtosos, the shape of the tail, how sharp the peak is
```sp.kurtosis(vals)```
here, -0.0762...