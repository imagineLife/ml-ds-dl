
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

## Customizing axis
```
axes = plt.axes()
axes.set_xlim([-5, 5])
axes.set_ylim([0, 1.0])
axes.set_xticks([-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5])
axes.set_yticks([0, 0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9, 1.0])
plt.plot(x, norm.pdf(x))
plt.plot(x, norm.pdf(x, 1.0, 0.5))
plt.show()
```
- plt.axes()
	- returns an axes object
- set_xlim
	- sets ranges
- set ylim
	- sets ranges
- set xticks
	- sets where ticks will be
- set yticks
	- sets y tick-marks

## GridLines
```
throw in a ....
axes.grid()
```
```
axes = plt.axes()
axes.set_xlim([-5, 5])
axes.set_ylim([0, 1.0])
axes.set_xticks([-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5])
axes.set_yticks([0, 0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9, 1.0])
axes.grid()
plt.plot(x, norm.pdf(x))
plt.plot(x, norm.pdf(x, 1.0, 0.5))
plt.show()
```

## Line Types && Colors
```
axes = plt.axes()
axes.set_xlim([-5, 5])
axes.set_ylim([0, 1.0])
axes.set_xticks([-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5])
axes.set_yticks([0, 0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9, 1.0])
axes.grid()
plt.plot(x, norm.pdf(x), 'b-') //blue solid
plt.plot(x, norm.pdf(x, 1.0, 0.5), 'r:') //red dashed
plt.show()
```


## Labeled Axes
```
axes = plt.axes()
axes.set_xlim([-5, 5])
axes.set_ylim([0, 1.0])
axes.set_xticks([-5, -4, -3, -2, -1, 0, 1, 2, 3, 4, 5])
axes.set_yticks([0, 0.1, 0.2, 0.3, 0.4, 0.5, 0.6, 0.7, 0.8, 0.9, 1.0])
axes.grid()
plt.xlabel('Greebles')
plt.ylabel('Probability')
plt.plot(x, norm.pdf(x), 'b-')
plt.plot(x, norm.pdf(x, 1.0, 0.5), 'r:')
plt.legend(['Sneetches', 'Gacks'], loc=4)
plt.show()
```


## XKCD style, 'cartoon-y'
```
plt.xkcd()
fig = plt.figure()
ax = fig.add_subplot(1, 1, 1)
ax.spines['right'].set_color('none')
ax.spines['top'].set_color('none')
plt.xticks([])
plt.yticks([])
ax.set_ylim([-30, 10])
data = np.ones(100)
data[70:] -= np.arange(30)
plt.annotate(
    'THE DAY I REALIZED\nI COULD COOK BACON\nWHENEVER I WANTED',
    xy=(70, 1), arrowprops=dict(arrowstyle='->'), xytext=(15, -10))
plt.plot(data)
plt.xlabel('time')
plt.ylabel('my overall health')
```


## Pie Chart
```
# Remove XKCD mode:
plt.rcdefaults()

# slice values
values = [12, 55, 4, 32, 14]

# slice colors
colors = ['r', 'g', 'b', 'c', 'm']

# which items are 'sticking out' from the pie
explode = [0, 0, 0.2, 0, 0]

#slice labels
labels = ['India', 'United States', 'Russia', 'China', 'Europe']

plt.pie(values, colors= colors, labels=labels, explode = explode)
plt.title('Student Locations')
plt.show()
```