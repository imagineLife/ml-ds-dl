# Pandas Overview
- A way of processing tabular data
- Will be used in tandem with [Scikit_learn](https://pypi.org/project/scikit-learn/)
	- usually takes an input of a numPy array   
- FLOW:
	- pandas loads/cleans data
	- translate to numPy arr
	- pass to sci-kit-learn 

### USING PANDAS IN PYTHON
```
%matplotlib inline
import numpy as np
import pandas as pd

# save file-data to var, using pandas read_file method
# assign to a DataFrame
df = pd.read_csv("PastHires.csv")

# output a short-exampe of the data
df.head()
```
- matplotlib is an import
	- graphs will appear in the notebook
- numpy as np (_alias_)
- pandas as pd (_alias_)
- pd.read_csv loads a csv file
	- saves as df var
	- first row is usually the titles of the table
	- save it as a **data-frame** 

### DataFrames
[docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html)
```...Two-dimensional, size-mutable, potentially heterogeneous tabular data.

Data structure also contains labeled axes (rows and columns). 
Arithmetic operations align on both row and column labels. 
Can be thought of as a dict-like container for Series objects. 
The primary pandas data structure.
```

### DataFrame data metadata
#### df.head()
- spits out a sample of the data
#### df.head(int)
- spits out a int-specific row number of the data
#### df.tail
- spits out the last 4 rows in the dataset
#### df.shape
- spits out something like ```(13,5)```, 13 rows, 5 columns
#### df.size
- number of unique data-points (13 * 5)
#### len(df)
- spits out number of rows
#### df.columns
- spits out column names

### DataFrame data manipulation
#### df[colName]
- get a specific column by name, returns a new dataFrame
#### df[colName][:int]
- returns a new dataFrame that is the :int number of rows in the colName column
#### df.size
- number of unique data-points (13 * 5)
#### len(df)
- spits out number of rows