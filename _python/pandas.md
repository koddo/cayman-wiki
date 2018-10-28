---
title:   "Pandas"
layout: default

---

# cheatsheet

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

<https://stackoverflow.com/questions/31593201/pandas-iloc-vs-ix-vs-loc-explanation-how-are-they-different/46915810#46915810>

- Q: How to create a series, a data frame? --- a: <https://pandas.pydata.org/pandas-docs/stable/10min.html#object-creation>
- Q: How to create a column based on other columns? --- a: `df.assign( col = df.col1 * df.col2 )`
- Q: `df['new_col'] = s` vs `df.assign( new_col = s )` --- a: The former has issues with indices??? Inplace vs a copy, the latter can be inlined

- Q: How to get columns? How to get index? How to get values? --- a: <https://pandas.pydata.org/pandas-docs/stable/10min.html#viewing-data>

- Q: How to rename a column in pandas? Inplace? --- a:
`df.rename( columns={'oldName1': 'newName1', 'oldName2': 'newName2'} )`, it can also be `inplace=True`
or with `df.set_axis(['a', 'b', 'c', 'd', 'e'], axis='columns', inplace=False)` --- <https://pandas.pydata.org/pandas-docs/stable/generated/pandas.Series.set_axis.html#pandas.Series.set_axis>
`df.columns = ['a', 'b', 'c']` is fine too.

- Q: `s.str.contains()` vs `substr in a_str` --- a:  

- Q: `DataFrame.merge()` vs `DataFrame.join()` --- a: Use `.merge`. `.join()` is the same as `.merge()`, but has other defaults.

- Q: How to sort data frame? By multiple columns? --- a: `df.sort_value(by='col')`, `df.sort_value(by=['col1', 'col2'])`


- Q: How to get non-null data? --- A: `df[ ~(df.col.isnull()) ]`

- Q: How to group by range of values? --- A: `df.groupby(pd.cut(df['Age'], bins=[15, 25, 35, 45, 55], right=False))`

Using format strings: <https://pandas.pydata.org/pandas-docs/stable/style.html#Finer-Control:-Display-Values>

- Q: How to change order of columns of a `DataFrame`?


- Q: How to get count, mean, standard deviation in `DataFrame`? --- A: `df.describe()`

- Q: `df[][] = 1` vs `df.loc['row', 'column'] = 1`? What is `SettingWithCopyWarning`? --- A: <https://pandas.pydata.org/pandas-docs/stable/indexing.html#indexing-view-versus-copy>

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=pandas">
    <p>Your browser does not support iframes.</p>
</iframe>







