---
title:   "Pandas"
layout: default

---

# cheatsheet

<https://github.com/pandas-dev/pandas/blob/master/doc/cheatsheet/Pandas_Cheat_Sheet.pdf>

<https://github.com/rougier/numpy-100>
<https://github.com/guipsamora/pandas_exercises>

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

## loc, iloc, at, iat

<https://stackoverflow.com/questions/31593201/pandas-iloc-vs-ix-vs-loc-explanation-how-are-they-different/46915810#46915810>

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

- Q: `df[][] = 1` vs `df.loc['row', 'column'] = 1`? What is `SettingWithCopyWarning`? --- A: <https://pandas.pydata.org/pandas-docs/stable/indexing.html#indexing-view-versus-copy>

- Q: Performance: `df.query` vs `df[boolean_expr]` vs `numexpr` vs `logical_and` --- A: <https://stackoverflow.com/questions/49936557/pandas-dataframe-loc-vs-query-performance>, <https://stackoverflow.com/questions/13611065/efficient-way-to-apply-multiple-filters-to-pandas-dataframe-or-series/30778300#30778300>
- Q: How to use `isin` in `df.query()` like this? `df[df['id'].isin(id_list)]` --- A: <https://stackoverflow.com/questions/33990955/combine-pandas-dataframe-query-method-with-isin>

- Q: How to get quantile of a DataFrame column? --- A: `dfc['height'].quantile(0.025)`

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


