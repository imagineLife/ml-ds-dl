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
```
sns.jointplot(x="Eng Displ", y="CombMPG", data=df)
```
## lmplot
- scatterplot with linear-regression line overlay 
	- ...fitting a best-fit line to the data
```
sns.lmplot(x="Eng Displ", y="CombMPG", data=df)
```
## Box && Whisker
```
sns.set(rc={'figure.figsize':(15,5)})
ax=sns.boxplot(x='Mfr Name', y='CombMPG', data=df)
ax.set_xticklabels(ax.get_xticklabels(),rotation=45)
```
- figure-size makes the thing bigger
- ax stores the boxplot itself
- the tick-labels are set from the ax.get_xticklabels()
	- rotated 45 degress

## Swarm Plot
```
ax=sns.swarmplot(x='Mfr Name', y='CombMPG', data=df)
ax.set_xticklabels(ax.get_xticklabels(),rotation=45)
```

## CountPlot
- a histogram... for categorical data
```
ax=sns.countplot(x='Mfr Name', data=df)
ax.set_xticklabels(ax.get_xticklabels(),rotation=45)
```


## Heatmap
```
df2 = df.pivot_table(index='Cylinders', columns='Eng Displ', values='CombMPG', aggfunc='mean')
sns.heatmap(df2)
```