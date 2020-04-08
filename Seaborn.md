# Seaborn
A MatPlotLib chart
```
%matplotlib inline

import pandas as pd

df = pd.read_csv("http://media.sundog-soft.com/SelfDriving/FuelEfficiency.csv")

gear_counts = df['# Gears'].value_counts()

gear_counts.plot(kind='bar')
```

## Upload Seaborn
```
import seaborn as sns
sns.set()
```
- makes matplotlib look better
- replaces default settings in matplotlib with seaborn settings

Now, same chart...
```
gear_counts.plot(kind='bar')
```
- ...looks nicer

## Seaborn has a distPlot
- a histogram with a line overlayed...
```
sns.distplot(df['CombMPG'])
```

## Pairplot (chart-matrix)
```
sns.pairplot(df2.head(300), hue='Cylinders', height=2.5);
```
- returns a 'grid' of charts... scatters, multi-series area, etc...

## Scatterplot
```
sns.scatterplot(x="Eng Displ", y="CombMPG", data=df)
```

## JointPlot
- interesting, scatterplot with 2 extra bar charts
	- one bar chart / histo above the scatter
	- one bar chart / histo to the right of the scatter, a horizontal bar

## lmplot
- scatterplot with linear-regression line overlay 
	- ...fitting a best-fit line to the data


