---
title:  "shad-prep-linal"
layout: default

---

* this line gets replaced with the generated table of contents
{:toc}

# 1

набор эквивалентных определений обратимости
Ax = 0 — это линейная комбинация столбцов: они все линейно независимы <=> существует только решение x=0


# 2

# 3

TODO: <https://ru.wikipedia.org/wiki/Определитель_Вандермонда>

# 4

$B \in M_n$, $\operatorname{rank}(B) = k$
$\operatorname{rank}(\hat{B}) \ = \ ?$
2:20:30

# 5

$\operatorname{dim} V = \operatorname{dim}\operatorname{Im} \alpha + \operatorname{dim}\operatorname{Ker} \alpha$


2:43:42 как находить собственные векторы
        единственное место, где нужна ФСР


1:22:42 линейный оператор в разных базисах, A' = C^{-1} A C
1:26:12 пример: сопряжены ли данные матрицы? ( 1 0 \\ 0 0 ) и ( 0 0 \\ 0 1 )
1:30:22 пример: сопряжены ли данные матрицы? ( 2 1 \\ 1 0 ) и ( 2 1 \\ 1 -1 )
1:31:26 можно составить и решить ситему с четыремя неизвестными, а можно посмотреть на инварианты:
        tr(C^{-1} A C) = tr(A)
        det(C^{-1} A C) = det(A)
        χ_{C^{-1} A C} (t) = χ_A (t) 


2:16:46 пример: дана матрица A = (1 2 3 4 \\ ... 16)_{4x4}, найдите rk(A^2019)
2:18:54 лемма о стабилизации

# Superlearn

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=shad-prep-linal">
    <p>Your browser does not support iframes.</p>
</iframe>
