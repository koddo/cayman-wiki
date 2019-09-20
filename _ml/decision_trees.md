---
title:   "Decision trees"
layout: default

---

# Sort this

<https://mlcourse.ai/articles/topic3-dt-knn/#Tree-building-Algorithm>

```
def build(L):
    create node t
    if the stopping criterion is True:
        assign a predictive model to t
    else:
        Find the best binary split L = L_left + L_right
        t.left = build(L_left)
        t.right = build(L_right)
    return t
```

# random forest

<https://machinelearningmastery.com/bagging-and-random-forest-ensemble-algorithms-for-machine-learning/>

`max_split`

    For classification a good default is: m = sqrt(p)
    For regression a good default is: m = p/3


# superlearn

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=ml -- decision trees">
    <p>Your browser does not support iframes.</p>
</iframe>

