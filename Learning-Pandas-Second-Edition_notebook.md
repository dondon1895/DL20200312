#panda0312
...
Chapter 2：啟動並運行pandas
...
```
# import numpy and pandas
import numpy as np
import pandas as pd

# used for dates
import datetime
from datetime import datetime, date

# Set some pandas options controlling output format
pd.set_option('display.notebook_repr_html', False)
pd.set_option('display.max_columns', 8)
pd.set_option('display.max_rows', 10)
pd.set_option('display.width', 80)

# bring in matplotlib for graphics
import matplotlib.pyplot as plt
%matplotlib inline
```
Pandas选项和自定义-https://www.yiibai.com/pandas/python_pandas_options_and_customization.html
pandas.set_option-https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.set_option.html

```
# create a four item Series
s = pd.Series([1, 2, 3, 4])
s
```
pandas.Series-https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.Series.html
Pandas的兩種資料類型-https://ithelp.ithome.com.tw/articles/10193394

```
# get value at label 1
s[1]
```

```
# return a Series with the row with labels 1 and 3
s[[1, 3]]
```

```
# create a series using an explicit index
s = pd.Series([1, 2, 3, 4], 
               index = ['a', 'b', 'c', 'd'])
s
```
https://www.geeksforgeeks.org/python-pandas-series/
Learning Pandas - Series、DataFrame、Index-https://ithelp.ithome.com.tw/articles/10204656

```
# look up items the series having index 'a' and 'd'
s[['a', 'd']]
```

```
# passing a list of integers to a Series that has
# non-integer index labels will look up based upon
# 0-based index like an array
s[[1, 2]]
```

```
# get only the index of the Series
s.index
```

```
# create a Series who's index is a series of dates
# between the two specified dates (inclusive)
dates = pd.date_range('2016-04-01', '2016-04-06')
dates
```
pandas.date_range-https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.date_range.html
pandas常用函数之date_range-https://blog.csdn.net/You_are_my_dream/article/details/70209757

```
# create a Series with values (representing temperatures)
# for each date in the index
temps1 = pd.Series([80, 82, 85, 90, 83, 87], 
                   index = dates)
temps1
```

```
# what's the temperation for 2016-4-4?
temps1['2016-04-04']
```

```
# create a second series of values using the same index
temps2 = pd.Series([70, 75, 69, 83, 79, 77], 
                   index = dates)
# the following aligns the two by their index values
# and calculates the difference at those matching labels
temp_diffs = temps1 - temps2
temp_diffs
```

```
# and also possible by integer position as if the 
# series was an array
temp_diffs[2]
```

```
# calculate the mean of the values in the Series
temp_diffs.mean()
```

