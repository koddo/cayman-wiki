---
title:  "Ya"
layout: default

---


<https://stanford.edu/~shervine/teaching/cs-229/cheatsheet-machine-learning-tips-and-tricks>

# optimization

<http://www.machinelearning.ru/wiki/index.php?title=момо>

One-dimentional optimization: 
<https://en.wikipedia.org/wiki/Golden-section_search>
<https://en.wikipedia.org/wiki/Successive_parabolic_interpolation>, <http://stu.sernam.ru/book_dig_m.php?id=93>
<https://en.wikipedia.org/wiki/Brent%27s_method>

Gradient, gradient descent.
<https://en.wikipedia.org/wiki/Gradient_method>
<http://wiki.fast.ai/index.php/Gradient_Descent>

<https://en.wikipedia.org/wiki/Newton%27s_method_in_optimization>, convergence rate

<https://en.wikipedia.org/wiki/Quasi-Newton_method>, <https://en.wikipedia.org/wiki/Limited-memory_BFGS>
<https://stats.stackexchange.com/questions/284712/how-does-the-l-bfgs-work>

Convex functions and sets, their properties: <http://www.machinelearning.ru/wiki/images/archive/8/87/20170921192058%21MOMO17_Seminar4.pdf>

≈<https://en.wikipedia.org/wiki/Constrained_optimization>, Karush–Kuhn–Tucker conditions, <https://en.wikipedia.org/wiki/Karush%E2%80%93Kuhn%E2%80%93Tucker_conditions>

<https://en.wikipedia.org/wiki/Linear_programming>
<https://en.wikipedia.org/wiki/Quadratic_programming>
<https://en.wikipedia.org/wiki/Quadratically_constrained_quadratic_program>

<https://en.wikipedia.org/wiki/Stochastic_gradient_descent>, modifications: momentum, RMSProp, Adam

# machine learning

1. <https://en.wikipedia.org/wiki/Linear_regression>, <https://en.wikipedia.org/wiki/Least_squares#Linear_least_squares>, gradient descent.

2. <https://en.wikipedia.org/wiki/Regularization_%28mathematics%29>
Linear regularization aka <https://en.wikipedia.org/wiki/Tikhonov_regularization>
Sparse models and l1 regularization: <https://medium.com/mlreview/l1-norm-regularization-and-sparsity-explained-for-dummies-5b0e4be3938a>
<https://stats.stackexchange.com/questions/45643/why-l1-norm-for-sparse-models>

3. <https://en.wikipedia.org/wiki/Linear_classifier>, margin: <http://www.machinelearning.ru/wiki/images/6/6d/Voron-ML-1.pdf#subsubsection.3.2.1>
обучение линейных классификаторов через вернюю оценку на долю ошибок, примеры верхних оценок

4. функционалы ошибки для классификации
<https://en.wikipedia.org/wiki/Confusion_matrix>
<https://en.wikipedia.org/wiki/Accuracy_and_precision>
<https://en.wikipedia.org/wiki/Precision_and_recall>
<https://en.wikipedia.org/wiki/F1_score>
ROC: <https://en.wikipedia.org/wiki/Receiver_operating_characteristic>, AUCROC: <https://stats.stackexchange.com/questions/132777/what-does-auc-stand-for-and-what-is-it>
precision recall curve, AUC of PR-curve (same as AUC-PR)
<https://stats.stackexchange.com/questions/7207/roc-vs-precision-and-recall-curves>
<https://stats.stackexchange.com/questions/123360/what-is-auc-of-pr-curve>

5. <https://en.wikipedia.org/wiki/Logistic_regression>
<http://www.machinelearning.ru/wiki/index.php?title=%D0%9B%D0%BE%D0%B3%D0%B8%D1%81%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B3%D1%80%D0%B5%D1%81%D1%81%D0%B8%D1%8F>
оценивание вероятностей
вывод логистической функция потерь из метода максимального правдоподобия

6. <https://en.wikipedia.org/wiki/Support_vector_machine>
<http://www.machinelearning.ru/wiki/index.php?title=SVM>
вывод постановки задачи для разделимого и неразделимого случаев
kernels and kernel tricks --- ядровый переход?

7. 

