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

корни характеристического и минимального совпадают
Ax = λx
A^k x = λ^k x -- this is used in the following polynomial
m(A) x = m(λ) x = 0


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
Basis in null space.


TODO:
1:22:42 линейный оператор в разных базисах, A' = C^{-1} A C
1:26:12 пример: сопряжены ли данные матрицы? ( 1 0 \\ 0 0 ) и ( 0 0 \\ 0 1 )
1:30:22 пример: сопряжены ли данные матрицы? ( 2 1 \\ 1 0 ) и ( 2 1 \\ 1 -1 )
1:31:26 можно составить и решить ситему с четыремя неизвестными, а можно посмотреть на инварианты:
        tr(C^{-1} A C) = tr(A)
        det(C^{-1} A C) = det(A)
        χ_{C^{-1} A C} (t) = χ_A (t) 


TODO:
2:16:46 пример: дана матрица A = (1 2 3 4 \\ ... 16)_{4x4}, найдите rk(A^2019)
2:18:54 лемма о стабилизации


TODO: Change of basis $A' = D^{-1} A C$


TODO: <https://en.wikipedia.org/wiki/Kronecker_product>

TODO: X^2 = A

# 6

$tr(A) = n_1 \lambda_1 + \ldots + n_k \lambda_k$
$det(A) = \lambda_1^{n_1} \cdots \lambda_k^{n_k}$
if there's a zero eigen value, then determinant is zero

P^2 = P and geometric definition

$\operatorname{diag}(a+bi, a-bi)$ can become real in some basis:

$$
\begin{pmatrix} 
a+bi & 0 \\
0 & a-bi
\end{pmatrix}
=
C^{-1}
\begin{pmatrix} 
a+bi & 0 \\
0 & a-bi
\end{pmatrix}
C
$$

# misc

orthogonal matrices rotate or mirror, but never stretch

нильпотентна => след нулевой — неплохая задача
спойлер: удостоверимся, что A^k = 0, значит A^n = 0, это дает собственные значения, затем приводим к жнф, у нее след такой же
спойлер: или отсюда следует: 1:59:19 (1) χ_A(λ) = λ^n - tr(A) λ^{n-1} + ... + (-1)^n det(A)

нильпотентна => след нулевой
более общий гроб: A \in M_n(R) нильпотентна тогда и только тогда, когда tr (A^k) = 0 для любого k <=n

# Superlearn

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=shad-prep-linal">
    <p>Your browser does not support iframes.</p>
</iframe>

