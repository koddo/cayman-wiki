---
title:  "Ya"
layout: default

---


<https://stanford.edu/~shervine/teaching/cs-229/cheatsheet-machine-learning-tips-and-tricks>

# probability and statistics

(1) Основы комбинаторики. Числа сочетания (с повторениями и без повторений), числа размещения (с повторениями и без повторений), перестановки. Бином Ньютона и биномиальные
коэффициенты. Формула включений и исключений. Простейшие комбинаторные тождества. Знакопеременные тождества. Использование формулы включений и исключений для
доказательства тождеств.
(2) Основы теории вероятностей. Классическое определение вероятности. Условные вероятности и независимость событий (попарная и в совокупности). Формулы полной вероятности
и Байеса.
(3) Случайные величины в дискретном вероятностном пространстве, их распределения. Независимость случайных величин. Числовые характеристики распределений: математическое
ожидание, дисперсия и ковариации. Основные свойства математического ожидания, дисперсии и ковариации.
(4) Случайные величины в произвольном вероятностном пространстве: определение и основные действия над случайными величинами. Функция распределения случайной величины,
ее основные свойства. Независимость случайных величин: эквивалентные определения.
(5) Определение математического ожидания в общем случае: аппроксимация простыми случайными величинами. Свойства математического ожидания. Абсолютно непрерывные случайные величины и векторы, примеры. Формулы подсчета математических ожиданий для
абсолютно непрерывного случая. Формула свертки.
(6) Виды сходимостей случайных величин. Три предельных теоремы: закон больших чисел
в форме Чебышјва, усиленный закон больших чисел в форме Колмогорова, центральная
предельная теорема для независимых одинаково распределенных случайных величин.
(7) Основы математической статистики. Основная задача математической статистики, понятие выборки. Эмпирическая функция распределения и еј свойства. Теорема ГливенкоКантелли. Теорема Колмогорова об эмпирической функции распределения. Критерий Колмогорова о проверке вида функции распределения.
(8) Основные свойства точечных оценок: несмещјнность, состоятельность, асимптотическая
нормальность. Методы построения: метод моментов и метод максимального правдподобия.
Свойства оценок указанных методов.
(9) Проверка статистических гипотез. Понятия статистического критерия, ошибок первого и
второго рода, функции мощности и уровня значимости критерия. Состоятельность и несмещенность статистического критерия. Критерий Неймана-Пирсона для проверки простых
гипотез. Асимптотический критерий хи-квадрат для полиномиальной схемы Бернулли, его
свойства.
(10) Проверка однородности нормальных выборок: критерий Фишера и t-критерий Стьюдента.
Критерий Аспина-Уэлча и t-критерий Стьюдента для связанных выборок. Проверка гипотезы об отсутствии сдвига для связанных выборок: критерий знаков, критерий знаковых
рангов Уилкоксона.

# optimization

(1) Методы одномерной оптимизации без производной: методы золотого сечения, парабол и
Брента.
(2) Градиентные методы обучения. Свойство градиента о направлении наискорейшего убывания. Градиентный спуск. Методы оценивания градиента.
(3) Метод Ньютона, его скорость сходимости.
(4) Квазиньютоновские методы оптимизации. Метод L-BFGS.
(5) Выпуклые множества и функции. Основные примеры. Операции, сохраняющие выпуклость. Простейшие свойства выпуклых функций.
(6) Задачи условной оптимизации. Условия Каруша-Куна-Таккера. Двойственность.
(7) Стандартные классы выпуклых задач: линейное программирование (LP), квадратичное
программирование (QP, QCQP).
(8) SGD и его основные модификации (momentum, RMSProp, Adam).

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

1. Линейная модель регрессии. Аналитическое решение для среднеквадратичной ошибки (с выводом). Градиентное обучение линейной регрессии.
<https://en.wikipedia.org/wiki/Linear_regression>, <https://en.wikipedia.org/wiki/Least_squares#Linear_least_squares>, gradient descent.
Least squares method comes from maximum likelyhood for linear regression.

2. Регуляризация линейных моделей. Разреженные модели и L1-регуляризация.
<https://en.wikipedia.org/wiki/Regularization_%28mathematics%29>
Linear regularization aka <https://en.wikipedia.org/wiki/Tikhonov_regularization>
Sparse models and l1 regularization: <https://medium.com/mlreview/l1-norm-regularization-and-sparsity-explained-for-dummies-5b0e4be3938a>
<https://stats.stackexchange.com/questions/45643/why-l1-norm-for-sparse-models>

3. Линейная модель классификации. Отступ. Обучение линейных классификаторов через верхнюю оценку на долю ошибок. Примеры верхних оценок.
<https://en.wikipedia.org/wiki/Linear_classifier>, margin: <http://www.machinelearning.ru/wiki/images/6/6d/Voron-ML-1.pdf#subsubsection.3.2.1>

4. Функционалы ошибки для классификации: матрица ошибок, accuracy, precision, recall, Fмера. ROC-кривая и AUC-ROC. Precision-recall-кривая и AUC-PR.
<https://en.wikipedia.org/wiki/Confusion_matrix>
<https://en.wikipedia.org/wiki/Accuracy_and_precision>
<https://en.wikipedia.org/wiki/Precision_and_recall>
<https://en.wikipedia.org/wiki/F1_score>
ROC: <https://en.wikipedia.org/wiki/Receiver_operating_characteristic>, AUCROC: <https://stats.stackexchange.com/questions/132777/what-does-auc-stand-for-and-what-is-it>
precision recall curve, AUC of PR-curve (same as AUC-PR)
<https://stats.stackexchange.com/questions/7207/roc-vs-precision-and-recall-curves>
<https://stats.stackexchange.com/questions/123360/what-is-auc-of-pr-curve>

5. Логистическая регрессия. Оценивание вероятностей. Вывод логистической функции потерь из метода максимального правдоподобия.
<https://en.wikipedia.org/wiki/Logistic_regression>
<http://www.machinelearning.ru/wiki/index.php?title=%D0%9B%D0%BE%D0%B3%D0%B8%D1%81%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B0%D1%8F_%D1%80%D0%B5%D0%B3%D1%80%D0%B5%D1%81%D1%81%D0%B8%D1%8F>
<https://www.quora.com/Why-is-logistic-regression-considered-a-linear-model>

6. Метод опорных векторов. Вывод постановки задачи для разделимого и неразделимого случаев. Ядра и ядровой переход.
<https://en.wikipedia.org/wiki/Support_vector_machine>
<http://www.machinelearning.ru/wiki/index.php?title=SVM>
вывод постановки задачи для разделимого и неразделимого случаев
kernels and kernel tricks --- ядровый переход?

7. Решающие деревья: определение и жадный алгоритм обучения. Функционал качества при выборе предиката. Общий вид критерия информативности (через функцию потерь) и конкретные примеры для регрессии (дисперсия) и классификации (критерий Джини и энтропийный критерий).
Decision tree, definition -- <https://en.wikipedia.org/wiki/Decision_tree_learning>
_Greedy_ learning algorithm -- <https://en.wikipedia.org/wiki/ID3_algorithm>
Функционал качества (?) при выборе предиката.
Критерий информативности (?), его общий вид (через функцию потерь)

8. Разложение ошибки на смещение и разброс.
Bias-variance decomposition -- <https://en.wikipedia.org/wiki/Bias–variance_tradeoff>
<https://habr.com/en/company/ods/blog/323890/#razlozhenie-oshibki-na-smeschenie-i-razbros-bias-variance-decomposition>

9. Бэггинг и случайные леса.
Bagging -- <https://en.wikipedia.org/wiki/Bootstrap_aggregating>
<https://en.wikipedia.org/wiki/Random_forest>

10. Градиентный бустинг. Обучение базовых алгоритмов для произвольной дифференцируемой функции потерь. Сокращение шага. Выбор прогнозов в листьях деревьев в градиентном бустинге.
<https://en.wikipedia.org/wiki/Gradient_boosting>
<http://blog.kaggle.com/2017/01/23/a-kaggle-master-explains-gradient-boosting/>
<https://machinelearningmastery.com/gentle-introduction-gradient-boosting-algorithm-machine-learning/>

11. Стекинг и блендинг.
Stacking and blending -- <https://en.wikipedia.org/wiki/Ensemble_learning#Stacking>
<https://stats.stackexchange.com/questions/18891/bagging-boosting-and-stacking-in-machine-learning>

12. Задача кластеризации. Метрики качества. Методы: K-Means, графовые методы, иерархическая кластеризация.
Clasterization.
<https://scikit-learn.org/stable/modules/clustering.html>
<http://www.machinelearning.ru/wiki/index.php?title=Кластеризация>
<https://neerc.ifmo.ru/wiki/index.php?title=Кластеризация>
Evaluation
<https://en.wikipedia.org/wiki/Cluster_analysis#Evaluation_and_assessment>
<https://neerc.ifmo.ru/wiki/index.php?title=Оценка_качества_в_задаче_кластеризации>
Methods: K-means, Graph-based models, Hierarchical clustering
<https://en.wikipedia.org/wiki/Category:Cluster_analysis_algorithms>

13. Задача визуализации, t-SNE.
Visualization
t-SNE, <https://en.wikipedia.org/wiki/T-distributed_stochastic_neighbor_embedding>
<https://www.coursera.org/lecture/unsupervised-learning/zadacha-vizualizatsii-hlvlT>
more:
<https://www.reddit.com/r/dataisbeautiful/comments/2o5qbu/interactive_subreddit_map_with_tsne_oc/>
<https://www.reddit.com/r/MachineLearning/comments/5ygh1q/d_data_preprocessing_tips_for_tsne/>
<https://www.reddit.com/r/MachineLearning/comments/70wlnm/p_want_to_understand_tsne_better_heres_a/>
<https://www.reddit.com/r/MachineLearning/comments/57gios/project_how_to_use_tsne_effectively/>


14. Обучение представлениеями и word2vec.
<http://mccormickml.com/2016/04/19/word2vec-tutorial-the-skip-gram-model/>

15. Понижение размерности. Метод главных компонент: постановка задачи и решение.

16. User-based и item-based рекомендательные системы.

17. Модели со скрытыми переменными (latent factor model, LFM) для построения рекомендаций. Обучение LFM: стохастический градиентный спуск, ALS, HALS.

18. Неявная информация в рекомендательных системах, implicit ALS.

19. Факторизационные машины. FFM. Способы обучения моделей.

20. Тематическое моделирование. Постановка задачи. Методы LSA, PLSA и LDA.

21. Нейронные сети. Метод обратного распространения ошибки.

22. Свјрточные и рекуррентные нейронные сети. Примеры архитектур, особенности обучения.

23. Backpropagation through time, пример вычисления градиентов, проблема затухающих градиентов.

24. Параллельное обучение линейных моделей (на одной машине и на кластере).

25. Концепция MapReduce.

26. Байесовский подход к теории вероятностей. Оценка параметров в байесовском и частотном
подходе. Примеры байесовских рассуждений.

27. Вероятностная модель линейной регрессии. Метод релевантных векторов для задачи регрессии.

28. ЕМ-алгоритм в общем виде. Примеры применения. Разделение смеси с помощью EMалгоритма.

# algorithms

Раздел 3. Алгоритмы и структуры данных

(1) Время и память как основные ресурсы. Модели вычислений: RAM, разрешающие деревья.
Сложность на заданном входе, сложность в худшем случае, сложность в среднем случае,
рандомизированная сложность. Нижняя оценка на число сравнений при сортировке в модели разрешающих деревьев.
(2) Динамическое программирование: общие принципы, свойства задач, эффективно решаемых при помощи динамического программирования. Рекурсивная реализация с мемоизацией и итеративная реализация. Примеры: вычисление редакционного расстояния, решение
задачи о рюкзаке.
(3) Жадные алгоритмы: общая идея, критерии применимости. Примеры: построение остовов
минимального веса в графах, жадные алгоритмы в задачах планирования. Жадный алгоритм на матроиде.
(4) Разновидности алгоритмов сортировки: inplace, stable. Быстрая сортировка (Quick-Sort).
Способы выбора разделяющего элемента. Элиминация хвостовой рекурсии.
(5) Порядковые статистики. Рандомизированный алгоритм Quick-Select. Детермининированный алгоритм поиска (метод "медианы медиан").
(6) Сортировка слиянием (Merge-Sort).
(7) Кучи: основные определения и свойства. Операции Sift-Down и Sift-Up. Бинарные и kичные кучи. Построение кучи за линейное время. Алгоритм сортировки Heap-Sort.
(8) Хеш-функции. Коллизии. Разрешение коллизий методом цепочек. Гипотеза простого равномерного хеширования, оценка средней длины цепочки.
(9) Универсальные семейства хеш-функций, оценка средней длины цепочки. Построение универсального семейства для целочисленных ключей. Совершенные хеш-функции. Построение совершенной хеш-функции методом двухуровненого хеширования.
(10) Фильтр Блюма (Bloom lter). Оценка вероятности ложноположительного срабатывания.
(11) Графы: основные определения и способы представления в алгоритмах. Обход в ширину.
Обход в глубину.
(12) Проверка на ацикличность и топологическая сортировка.
(13) Деревья поиска. Вставка и удаление элементов. Inorder-обход дерева.
(14) Сильно связные компоненты и топологическая сортировка конденсации.
(15) Дерево отрезков.
(16) Кратчайшие пути в графах. Оценки расстояний и их релаксация. Алгоритмы Беллмана
Форда, Флойда и Дийкстры.
(17) Остовы минимального веса. Лемма о минимальном ребре в разрезе. Алгоритмы Краскала
и Прима.
(18) Системы непересекающихся множеств. Реализация с использованием леса. Ранги вершин,
эвристика ранга. Логарифмическая оценка ранга через количество элементов. Эвристика
сжатия путей. Оценка учетной стоимости операций (без доказательства).
