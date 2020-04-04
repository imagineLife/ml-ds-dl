
# Mean, Median & Mode
- Model 10k people && their income each year
```
import numpy as np

incomes = np.random.normal(27000, 15000, 10000)
np.mean(incomes)
```
- **numpy random.normal** 
	- creates a bell-curve of data with an normal distribution
	- 27000 is the **middle**
	- 15000 is the **standard deviation**
	- 10K **points**
```
np.mean(incomes)
```
returns 26993.72...


## See distribution of data
```
%matplotlib inline
import matplotlib.pyplot as plt
plt.hist(incomes, 50)
plt.show()
```
- import matplotlib (inline)
- set pyplot as plt
- create a histogram
	- incomes dataset
	- 50 buckets (bars)
- plt.show
	- renders a chart

## Mocking data _(using NumPy)_
incomes = np.random.normal(100.0, 20.0, 10000)
- .random creates random values
- .normal creates the normally distributed dataset

## Finding Mean _(using NumPy)_
- np.mean(incomes)
	- incomes is an array
## Finding Median
- np.median(incomes)
	- incomes is an array