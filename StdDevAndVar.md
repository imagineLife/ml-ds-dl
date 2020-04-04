# Standard Deviation && Variance
- the 'spread' of the data
- the 'shape' of the dataset

## Measuring Variance
"sigma squared"
"average of the squared differences from the mean"
Ex.
```
let peopleInLinePerHour = [1,4,5,4,8]
1. Find the mean
  - 1+4+5+4+8 = 22
  - 22 / 5 = 4.4
  - 4.4
2. Find the DIFFERENCES from the mean @ each point
  - [-3.4, -.4, .6, -.4, 3.6]
3. find the SQUARED diffs
  - [ 11.56, .16, .36, .16, 12.96]
4. find the AVG of those SQUARED Diffs
  - 11.56 + .16 + .36 + .16 + 12.96  = 25.2
  - 25.2 / 5 = 5.04
  - 5.04
```
The Variance is 5.04

## Standard Deviation
the sq of the variance
sq.root of 5.04 = 2.24


## Population vs. Sample Variances
### Population
do as above
### Sample Variance
- taking a subset of the data, usually to make computing easier


## In Python
#### Build some data
```
%matplotlib inline
import numpy as np
import matplotlib.pyplot as plt

incomes = np.random.normal(100.0, 50.0, 10000)

plt.hist(incomes, 50)
plt.show()
```
- import matplotlib, to draw the thing
- import numpy to math the thing
- import the pyplot subset as plt
- build normal-distribution of data...
	- 10K points
	- centered around 100
	- st.dev of 20

#### Compute Std. Deviation
```
incomes.std()
```
returns 49.576...in
#### Compute Variance
```
incomes.var()
```
2499.1424....