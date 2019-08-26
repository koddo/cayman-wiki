---
title:  "Linear algebra -- linear independence and rank"
layout: default

---

* this line gets replaced with the generated table of contents
{:toc}

# Properties of rank

<https://en.wikipedia.org/wiki/Rank–nullity_theorem>: $\operatorname{dim} V = \operatorname{dim}\operatorname{Im} \alpha + \operatorname{dim}\operatorname{Ker} \alpha$

$\operatorname{rk}(A^2) \leq \operatorname{rk}(A)$ — <https://math.stackexchange.com/questions/1918440/for-any-square-matrix-a-show-that-rka2-leq-rk-a>

Frobenius Inequality Rank: $\operatorname{rk}(AB)+\operatorname{rk}(BC)\leq \operatorname{rk}(B)+\operatorname{rk}(ABC)$
<https://math.stackexchange.com/questions/497830/frobenius-inequality-rank>

$\vert \operatorname{rk}A - \operatorname{rk}B \vert \leq \operatorname{rk}(A+B) \leq \operatorname{rk}A + \operatorname{rk}B$
This means that if you mingle $A$ with $B$, it's rank is going to change not more than rank of $B$ in both direction.
Left inequality is a corollary of the right one: let $A = X-Y$ and $B = Y$, then $\operatorname{rk}(X-Y) \geq \operatorname{rk}X - \operatorname{rk}(Y)$.
Chagnge $Y = -Y$, get $\operatorname{rk}(X+Y) \geq \operatorname{rk}X - \operatorname{rk}(Y)$.
This we can exchange $X$ and $Y$, the expression is symmetrical, get $\operatorname{rk}(X+Y) \geq \operatorname{rk}(Y) - \operatorname{rk}X$
Which means $\operatorname{rk}(X-Y) \geq \vert \operatorname{rk}X - \operatorname{rk}(Y) \vert$

$\operatorname{rk} A + \operatorname{rk}B - n \leq \operatorname{rk} AB \leq \operatorname{min}(\operatorname{rank}(A), \operatorname{rank}(B))$
Left inequality can also be written as $\operatorname{Ker}A + \operatorname{Ker}B \geq \operatorname{Ker}AB$
<https://math.stackexchange.com/questions/298836/sylvester-rank-inequality-operatornamerank-a-operatornamerankb-leq-o>
<https://math.stackexchange.com/questions/978/how-to-prove-and-interpret-operatornamerankab-leq-operatornamemin-ope?noredirect=1&lq=1>

For square matrix $A$ of size $n$: $\operatorname{rank}(A^n) = \operatorname{rank}(A^{n+1})$ -- <https://math.stackexchange.com/questions/298041/given-a-square-matrix-a-of-order-n-prove-operatornamerankan-operatorn?noredirect=1&lq=1>

Prove $\operatorname{rank}(A) = \operatorname{rank}(AA^T) = \operatorname{rank}(A^TA)$ -- <https://math.stackexchange.com/questions/215145/rank-of-product-of-a-matrix-and-its-transpose/682249#682249>

# Properties of kernel

## dim ker A^2 <= 2 dim ker A

А это ровна та картинка, что в доказательстве ЖНФ используется =)

Тут есть несколько способов это доказывать. Но самый простой -- через ЖНФ. Тебе достаточно считать, что A имеет жорданову нормальную форму и тогда показать нужное неравенство. Для этого надо рассмотреть клетку вида J_k(s) и понять как связаны dim ker J_k(s) и dim ker J_k(s)^2. Если s не ноль, то оба равны нулю, если s = 0, то тут зависит от k. Если k >=2, то 2 dim ker J_k(0) = dim ker J_k(0)^2, если k = 1, то dim ker J_k(0) = dim ker J_k(0). Это делается выписыванием явно условия на клетку. Отсюда и нужное неравенство.

Другой способ такой. Нам надо показать, что ядро A занимает не меньше половины ядра A^2. Представим ker A^2 = ker A + <v_1,...,v_s>, где сумма прямая, а v_i -- базис линейной оболочки. Тогда надо увидеть, что векторы Av_1,...,Av_s лежат в ker A и линейно независимы, а это и означает, что ker A занимает не меньше половины ker A^2.


# Superlearn

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- linear algebra -- linear independence and rank">
    <p>Your browser does not support iframes.</p>
</iframe>

