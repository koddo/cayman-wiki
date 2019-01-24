---
title:  "Graph theory"
layout: default

---

# ?

<https://en.wikipedia.org/wiki/Path_(graph_theory)>

Path
Simple path
Cycle
<https://ru.wikipedia.org/wiki/Связный_граф#Некоторые_критерии_связности>

<https://en.wikipedia.org/wiki/Path_(graph_theory)>

- Q: How to check a graph for connectivity? Complexity of algorithm?
<https://en.wikipedia.org/wiki/Connectivity_(graph_theory)>

<https://en.wikipedia.org/wiki/Topological_sorting>

# Directed graphs

- Q: What is _connected_ graph? --- A: A graph is _connected_ when there is a path between every pair of vertices.

- Q: hw problems 107

- Q: Graph theory: path, simple path, Eulerian path, Hamiltonian path, diameter?

- Q: Prove that every tree with at least two vertices have at least two leaves.
- A: Used here: if there are no hanging vertices in a graph, it's not a tree, so it has a simple cycle.
<https://www.quora.com/How-would-we-prove-that-every-tree-with-at-least-two-vertices-have-at-least-two-leaves>
Maybe: 
<https://math.stackexchange.com/questions/1127514/every-tree-has-two-leaves-is-my-proof-ok>
<https://math.stackexchange.com/questions/732734/a-tree-has-at-least-two-leafs-proof-by-contradiction>
<https://math.stackexchange.com/questions/1746743/prove-that-trees-have-at-least-two-vertices-of-degree-one>
<https://brainly.com/question/7304488>
<https://math.stackexchange.com/questions/689010/graph-theory-tree-has-at-least-2-vertices-of-degree-1>

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- graph theory -- problems">
    <p>Your browser does not support iframes.</p>
</iframe>

# Undirected graphs

IMPORTANT: Здесь граф --- неориентированный, без петель и кратных ребер.

- Q: В стопке $n$ карточек, у каждой из которых на двух сторонах написано по числу от 1 до $n$, причем все числа написаны по два раза. Докажите, что карточки можно разложить на столе так, чтобы все числа сверху были различны.
- A: hw121 --- <http://www.problems.ru/view_problem_details_new.php?id=31079>

- Q: Приведите пример графа (или докажите, что его не существует), степени вершин которого равны (1,1,1,2,3,3,4).
- A:
<https://stackoverflow.com/questions/14736909/construct-a-graph-from-given-node-degrees>
<https://en.wikipedia.org/wiki/Degree_(graph_theory)#Degree_sequence>
<http://stu.alnam.ru/book_grnet-67>

- Q: В компании у каждых двух людей ровно пять общих знакомых. Докажите, что 
количество пар знакомых делится на 3.
- A: hw131 <http://www.problems.ru/view_problem_details_new.php?id=35438>

- Q: В графе из $2n+1$ вершин для любого подмножества из $n$ вершин найдется отличная от них вершина, соединенная с каждой вершиной подмножества. Докажите, что есть вершина, соединенная со всеми остальными.
- A: hw132 --- <http://math.hashcode.ru/questions/67493/олимпиада-покрытия-в-графах>

- Q: При дворе короля Артура собрались 2n рыцарей, причём каждый из них имеет среди присутствующих не более  n – 1  врага. Доказать, что Мерлин, советник Артура, может так рассадить рыцарей за круглым столом, что ни один из них не будет сидеть рядом со своим врагом.
- A: old exam problems 23 --- <http://www.problems.ru/view_problem_details_new.php?id=78548>

- Q: Вершины неориентированного графа (`n` штук) расположены на окружности и соединены через одну и через `3` (соседние вершины не соединены). При каких `n` в этом графе существует эйлеров цикл?
  A: old exam problems 24 --- похожая: <http://eek.diary.ru/p195107196.htm>
  
  


# Paths, cycles, connectivity

<https://en.wikipedia.org/wiki/Eulerian_path>
<https://en.wikipedia.org/wiki/Hamiltonian_path>

- Q: hw problems 133-157


- Q: Существует в графе "каркас куба" путь, проходящий через одну из вершин 25 раз, а через остальные - по 30?
- A: old exam problems 19  <https://dxdy.ru/topic30990.html>
Можно разбить вершины куба на две четверки попарно несоседних вершин и заметить, что суммы прохождений по вершинам четверок различаются не более чем на 1.

<https://en.wikipedia.org/wiki/Biconnected_component>
<https://ru.wikipedia.org/wiki/Шарнир_(теория_графов)>

# Isomorphisms

<https://en.wikipedia.org/wiki/Graph_isomorphism>
<https://en.wikipedia.org/wiki/Graph_isomorphism_problem>

- Q: hw problems 158-161

# Bipartite graphs

<https://en.wikipedia.org/wiki/Bipartite_graph>
<https://ru.wikipedia.org/wiki/Двудольный_граф>

- Q: hw problems 162-167

# Eulerian and Hamiltonian graphs

<http://mathworld.wolfram.com/EulerGraph.html>
<http://mathworld.wolfram.com/EulerianGraph.html>

- Q: hw problems 168-180

# Trees

<https://en.wikipedia.org/wiki/Tree_(graph_theory)>

Tree is a connected, undirected graph without cycles.

Trees of $n$ vertices have $n-1$ edges.

- Q: Trees of $n$ vertices have $n-1$ edges. --- A: <http://compalg.inf.elte.hu/~tony/Oktatas/TDK/FINAL/Chap 4.PDF>, page 2
- Q: Any connected graph with $n$ vertices and $n-1$ edges is a tree. --- A: <http://compalg.inf.elte.hu/~tony/Oktatas/TDK/FINAL/Chap 4.PDF>, page 2
- Q: there's more

- Q: hw problems 181-198

# Spanning trees

<https://en.wikipedia.org/wiki/Spanning_tree>

- Q: hw problems 199-202

# Planar graphs and Euler's theorem

<https://en.wikipedia.org/wiki/Planar_graph>
<https://en.wikipedia.org/wiki/Planar_graph#Euler's_formula>
<https://en.wikipedia.org/wiki/Euler_characteristic#Plane_graphs>
<https://math.stackexchange.com/questions/261227/understanding-the-proof-of-eulers-formula>

- Q: $V-E+F=2$

- Q: hw problems 203-219

# Diameter, center

- Q: Диаметр графа равен двум, степень вершин — не больше 3. Какое наибольшее количество вершин может быть в графе?
- A: Если такой граф существует, то дерево путей минимальной длины из центра будет обладать тем же свойством.
Рассмотрим центр. Он соединен с неболее, чем 3 вершинами, каждая из которых соединена еще не более,чем с двумя. Итого 10.
???


# ?

<https://ru.wikipedia.org/wiki/Теорема_Понтрягина_—_Куратовского>
<http://neerc.ifmo.ru/wiki/index.php?title=Теорема_Понтрягина-Куратовского>
<https://en.wikipedia.org/wiki/Kuratowski's_theorem>





Graph diameter
- Q: Number of diameters if a full binary tree?




# Questions

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- graph theory">
    <p>Your browser does not support iframes.</p>
</iframe>

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- graph theory -- problems">
    <p>Your browser does not support iframes.</p>
</iframe>

