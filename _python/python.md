---
title:  "Python"
layout: default

---

# Later

<https://gto76.github.io/python-cheatsheet/>


- Q: How to test against True, False, None? --- A: <https://stackoverflow.com/questions/9494404/use-of-true-false-and-none-as-return-values-in-python-functions>
- A: 
This is a mess in the python language.
But to simplify things let's just declare you should only use `if var: ...`.
(And other forms when you know what you're doing.)

According to PEP-8:

```
Don't compare boolean values to True or False using ==.

Yes:   if greeting:
No:    if greeting == True:
Worse: if greeting is True:
```

The problem is that we sometimes want to distinguish truthy values like `True`, `1`, `['a']`, `range(10)`, etc.

`if var is True: ...` actually works, but relies on 

<https://hackernoon.com/understanding-the-underscore-of-python-309d1a029edc>
<https://www.reddit.com/r/Python/comments/6cvx0s/the_meaning_of_underscores_in_python>


# Data classes and named tuples

<https://realpython.com/python-data-classes/>

Named tuples behave like tuples by design. We can compare two tuples of different types:

```
Aaa(1, 'a') == Bbb(1, 'a')     # True
```



