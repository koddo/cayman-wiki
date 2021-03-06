---
title:   "Pandas"
layout: default

---

# cheatsheet

<https://github.com/pandas-dev/pandas/blob/master/doc/cheatsheet/Pandas_Cheat_Sheet.pdf>

<https://github.com/rougier/numpy-100>
<https://github.com/guipsamora/pandas_exercises>

Brandon Rhodes - Pandas From The Ground Up - PyCon 2015: <https://www.youtube.com/watch?v=5JnMutdy6Fw>, <https://github.com/brandon-rhodes/pycon-pandas-tutorial>
```
len(df)
df.head(), df.tail()
df['column'], df.column

s + value
s1 + s2
s.notnull(), s.isnull()

df.sort_values(ascending=False)
s.sort_values(by='col')

df[ df.col == value ]
df[ (v1 < df.c) & (df.c < v2) ]

df[ ~df['type'].isin(['actor', 'actress']) ]   # plain not in doesn't work
df = df[ df['title'].str.startswith('Hamlet') ]

df[ ['col1', 'col2'] ]

s.value_counts().sort_index()   # dropna=True by default
                                # it's like s.groupby('col').size()

s.str.len()
s.str.contains()
s.str.startswith()

s = s.unique()
s = s.sort_values(by=['year', 'name'])


df.plot()
s.plot(kind='bar')
titles.year.value_counts().sort_index().plot()

%%time df[ df.title == 'Hamlet' ]
c = cast.set_index(['title']).sort_index()
c.loc('Hamlet')
c = cast.set_index(['title', 'year']).sort_index()
c.loc['Hamlet'].loc['1972']
c.loc[('Hamlet', '1972')]
reset_index

df.groupby('col')
df.groupby(['col1', 'col2])
cols = ['col1', 'col2]; df.sort_values(by=cols)[cols]   # to preview what's getting into the groups
.size(), .min(), .max(), .mean(), .agg(['min', 'max'])


???:
df.unstack()
df.stack()

df.fillna()

df.where()??
```

<https://pandas.pydata.org/pandas-docs/stable/comparison_with_sql.html>

Exercises-3.ipynb: `t = titles; t[t.title == 'Hamlet'].groupby( t.year // 10 * 10 ).size().sort_index().plot(kind='bar')`
Exercises-4.ipynb: `cast.groupby(['year', 'type']).size().unstack('type').fillna(0).plot(kind='area')`

```
  len(df)       series + value    df[df.c == value]
  df.head()     series + series2  df[(df.c >= value) & (df.d < value)]
  df.tail()     series.notnull()  df[(df.c < value) | (df.d != value)]
  df.COLUMN     series.isnull()   df.sort_values('column')
  df['COLUMN']  series.order()    df.sort_values(['column1', 'column2'])

  s.str.len()        s.value_counts()
  s.str.contains()   s.sort_index()    df[['column1', 'column2']]
  s.str.startswith() s.plot(...)       df.plot(x='a', y='b', kind='bar')

  df.set_index('a').sort_index()        df.loc['value']
  df.set_index(['a', 'b']).sort_index() df.loc[('v','u')]
  df.groupby('column')                  .size() .mean() .min() .max()
  df.groupby(['column1', 'column2'])    .agg(['min', 'max'])

  df.unstack()      s.dt.year       df.merge(df2, how='outer', ...)
  df.stack()        s.dt.month      df.rename(columns={'a': 'y', 'b': 'z'})
  df.fillna(value)  s.dt.day        pd.concat([df1, df2])
  s.fillna(value)   s.dt.dayofweek
```

## misc

remove a column: `df.drop(columns, axis=1, inplace=True)`


## apply, applymap, map

```
s = pd.Series([1, 2, 3])
sa = s.apply(lambda x: pd.Series([x, x]))
sm =   s.map(lambda x: pd.Series([x, x]))

type(sa) == pd.DataFrame
type(sm) == pd.Series
all( type(sm[i]) == pd.Series for i in range(len(sm)) )
```

## concat vs append

<https://stackoverflow.com/questions/15819050/pandas-dataframe-concat-vs-append/48168086#48168086>

# `DataFrame.loc` vs `iloc` vs `at` vs `iat` vs `ix` vs indexing operator `df[]`, peculiarities about slicing

<https://stackoverflow.com/questions/28757389/pandas-loc-vs-iloc-vs-ix-vs-at-vs-iat/47098873#47098873>

`loc` is label based. Accepts a single label, a list of labels, a slice, a boolean array, a callable.

WARNING: When slicing by label, `loc` includes both start and stop values.

Raises `KeyError`.

```
df.loc['viper']
df.loc[['viper', 'sidewinder']]
df.loc['cobra':'viper', ['food', 'score']]
df.loc[df['shield'] > 6]
df.loc[lambda df: df['shield'] == 8]

df.loc['cobra'] = 10           # set entire row
df.loc[:, 'max_speed'] = 30    # set entire column
```

`iloc` is position based. Accepts an integer, a list of integers, a slice, a boolean array, and a callable.

Raises `IndexError` just like lists in python, when accessing out of range index, but not when using slicing.

```
df.iloc[[2, 3], [1, 2]]
df.iloc[1:5, 2:4]
```

`at` and `iat` are for accessing a single cell.

```
df.at['Christina', 'favorite color']
df.loc[5].at['B']     # Get value within a Series
df.iat[2, 5]
```

`ix` is deprecated.

Indexing operator `[]` is mostly for selecting columns, but confusingly selects rows by slicing:

```
df['height']                  # one columns
df[['height', 'weight']]      # two columns
df['Penelope':'Christina'] # _rows_
```

# `SettingWithCopyWarning`

<https://pandas.pydata.org/pandas-docs/stable/indexing.html#indexing-view-versus-copy>

<https://www.dataquest.io/blog/settingwithcopywarning/>
false negative:

```
data.loc[data.bidder == 'parakeet2004', ('bidderrate', 'bid')]['bid'] = 5.0
data.loc[data.bidder == 'parakeet2004', ('bidderrate', 'bid')]
```

<https://stackoverflow.com/questions/20625582/how-to-deal-with-settingwithcopywarning-in-pandas/53954986#53954986>
In general, you should use loc for label-based assignment, and iloc for integer/positional based assignment, as the spec guarantees that they always operate on the original. Additionally, for setting a single cell, you should use at and iat.

# Questions

- Q: How to create a series, a data frame? --- a: <https://pandas.pydata.org/pandas-docs/stable/10min.html#object-creation>
- Q: How to create a column based on other columns? --- a: `df.assign( col = df.col1 * df.col2 )`; `df.assign(**{'- colname -' : col1*col2})` if you'd like an arbitrary name.
- Q: `df['new_col'] = s` vs `df.assign( new_col = s )` --- a: The former has issues with indices??? Inplace vs a copy, the latter can be inlined.

- Q: How to get columns? How to get index? How to get values? --- a: <https://pandas.pydata.org/pandas-docs/stable/10min.html#viewing-data>



- Q: `s.str.contains()` vs `substr in a_str` --- a:  

- Q: `DataFrame.merge()` vs `DataFrame.join()` --- a: Use `.merge`. `.join()` is the same as `.merge()`, but has other defaults.

- Q: How to sort data frame? By multiple columns? --- a: `df.sort_value(by='col')`, `df.sort_value(by=['col1', 'col2'])`


- Q: How to get non-null data? --- A: `df[ ~(df.col.isnull()) ]`

- Q: How to group by range of values? --- A: `df.groupby(pd.cut(df['Age'], bins=[15, 25, 35, 45, 55], right=False))`

Using format strings: <https://pandas.pydata.org/pandas-docs/stable/style.html#Finer-Control:-Display-Values>

- Q: How to change order of columns of a `DataFrame`?


- Q: How to get count, mean, standard deviation in `DataFrame`? --- A: `df.describe()`


- Q: Performance: `df.query` vs `df[boolean_expr]` vs `numexpr` vs `logical_and` --- A: <https://stackoverflow.com/questions/49936557/pandas-dataframe-loc-vs-query-performance>, <https://stackoverflow.com/questions/13611065/efficient-way-to-apply-multiple-filters-to-pandas-dataframe-or-series/30778300#30778300>, <https://pandas.pydata.org/pandas-docs/stable/generated/pandas.DataFrame.query.html>
- Q: How to use `isin` in `df.query()` like this? `df[df['id'].isin(id_list)]` --- A: <https://stackoverflow.com/questions/33990955/combine-pandas-dataframe-query-method-with-isin>

- Q: What is `ufunc` in `numpy`? 
- A: <https://jakevdp.github.io/PythonDataScienceHandbook/02.03-computation-on-arrays-ufuncs.html>, <https://docs.scipy.org/doc/numpy-1.12.0/reference/ufuncs.html>, <http://www.scipy-lectures.org/advanced/advanced_numpy/index.html#universal-functions>

- Q: 
- A: 


<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=pandas">
    <p>Your browser does not support iframes.</p>
</iframe>


# snippets

```
from IPython.core.interactiveshell import InteractiveShell
InteractiveShell.ast_node_interactivity = "all"

%matplotlib inline
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

# split-apply-combine

```
df.groupby('species').sum()['sepal_width'] # ← BAD!
df.groupby('species')['sepal_width'].sum() # ← BETTER & FASTER!
df.groupby('species').[['sepal_width']].sum()```

multicol_sum = df.groupby(['species', 'petal_width']).sum()
multicol_sum.xs('virginica', level='species')



def foo(gr):
  print(type(gr))
  return None
 
df.groupby('species').apply(foo)

def foo(gr): 
  print(gr, '\n')
 
df.groupby('species').apply(func=foo)

```

apply calls func twice on the first row

# numpy



