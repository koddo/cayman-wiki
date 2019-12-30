---
title:   "Misc"
layout: default

---

# Recall and Precision

<https://medium.com/@klintcho/explaining-precision-and-recall-c770eb9c69e9>

TODO: draw own pictures, <https://youtu.be/sarVw-iVWgc?list=PLiaHhY2iBX9ihLasvE8BKnS2Xg8AhY6iV&t=308>
TODO: examples
TODO: examples of high/low recall and precision

# Logistic regression

Logistic function $$\sigma(x) = \frac{1}{1+e^{-x}}$$

# Metrics

Confusion matrix

Accuracy

Precision, Recall

AUC ROC

## F_1

<https://stackoverflow.com/questions/26355942/why-is-the-f-measure-a-harmonic-mean-and-not-an-arithmetic-mean-of-the-precision>

> If you want to know if your predictions are good, you need these two measures. 
> If one of these two values decreases dramatically, the f-score also does.

<https://www.quora.com/What-is-an-intuitive-explanation-of-F-score>

> When measuring how well you're doing, it's often useful to have a single number to describe your performance. 

<https://www.mikulskibartosz.name/f1-score-explained/>

![f_{1} score](https://www.mikulskibartosz.name/assets/images/2019-02-04-f1-score-explained/f1_score.png)

![f_{2} score](https://www.mikulskibartosz.name/assets/images/2019-02-04-f1-score-explained/f2_score.png)

![f_{0.5} score](https://www.mikulskibartosz.name/assets/images/2019-02-04-f1-score-explained/f05_score.png)

Why harmonic mean:

> The harmonic mean is the equivalent of the arithmetic mean for reciprocals of quantities that should be averaged by the arithmetic mean
> Precision and the recall are "naturally" reciprocals because their numerator is the same and their denominators are different. Fractions are more sensible to average by arithmetic mean when they have the same denominator.

# superlearn

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=ml -- misc">
    <p>Your browser does not support iframes.</p>
</iframe>

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=ml -- metrics">
    <p>Your browser does not support iframes.</p>
</iframe>
