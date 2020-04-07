# Percentiles
99th percentile is the top 1%
50th percentile is the median. half above, half below

# Quartiles
4 quartiles.
divide the toal in 4, 25% at a time.
q1-q3 contain 50% 
The **inter-quartile range** is the middle that contains the middle 50% of the data distribution.

## Percentiles in python
generating randomly distributed normalized data...
```
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt

vals = np.random.normal(0, 0.5, 10000)

plt.hist(vals, 50)
plt.show()
```

### Computing percentiles of the data distribution with NumPy
```
np.percentile(vals, 50)
```
**npm.percentile(data, percVal)**


