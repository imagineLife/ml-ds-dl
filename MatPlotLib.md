
# MatPlotLib
## Line graph
```
%matplotlib inline
from scipy.stats import norm
import matplotlib.pyplot as plt
import numpy as np

x = np.arange(-3, 3, 0.01)
lineData = norm.pdf(x)

plt.plot(x, lineData)
plt.show()
```
- **arange** makes the x-axis "scale" from -3 to 3, with increments of .001
	- left-bound (-3)
	- right-bound (3)
	- increment(.001)
- **plot** plot the thing
	- x, as the x scale

### Multi-Line
```
%matplotlib inline
from scipy.stats import norm
import matplotlib.pyplot as plt
import numpy as np

x = np.arange(-3, 3, 0.01)
lineData = norm.pdf(x)
lineTwoData = norm.pdf(x, 1.0, 0.5)
plt.plot(x, lineData)
plt.plot(x, lineTwoData)
plt.show()
```
- NEW CONTENT
	- another distribution 
	- with a mean around 1
	- standard deviation of 0.5
- Auto-coloring

## Saving Chart to a file
```
plt.plot(x, lineData)
plt.plot(x, lineTwoData)
plt.savefig('/Users/Jake/Desktop/projects/ml-ds-dl/MyPlot.png', format='png')
```
- MAC SHORTCUT NOTE
	- open the file in a finder
	- assure that the lower path-bar is visible in the finder window
	- right-click the file in the file-path bar
	- select 'copy as "Pathname"'