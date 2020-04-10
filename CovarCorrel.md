you cannot say anything about causality without an experiment,
but correlation can tell you which experiments you may want to run!

# Covariance
- on each attr of the dataset
	- compute variance from the mean
- take these variances, && take the 'dot product' between the variacnes
	- dot product / sample size = covariant amount

**PROBLEM**
- may be difficult to understand

# Correlation
- may be simpler than covariance
- correlation of 0 means no connection/similarities
- correlation of 1 means exactly related variables

**REMEMBER!!**
- correlation DOES NOT IMPLICITLY IMPLY CAUSALITY


# Calculating these using python
### Mean Deviation
```
def mean_deviation(x):
    xmean = mean(x)
    return [xi - xmean for xi in x]
```
- create new list
- loop through x array
- call each element xi
- on each iteration
	- return element - xmean
- return difference between the element and the mean in the dataset

### Covariance
- will perform the mean_deviation on an x-set of data && a y-set of data

```
def covariance(x, y):
    n = len(x)
    return dot(mean_deviation(x), mean_deviation(y)) / (n-1)
```