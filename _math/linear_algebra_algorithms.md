---
title:  "Linear algebra"
layout: default

---

* this line gets replaced with the generated table of contents
{:toc}

# ?

- Q: In a set of vectors $v_1, \ldots, v_m \in \mathbb{R^n}$ find a basis and express others as linear combinations.
A: 

- Q: Find some basis in a span $V = \langle v_1, \ldots ,v_m \rangle$, where $v_i \in \mathbb{R^n}$.

- Q: Extend a set of linear independent vectors $v_1, \ldots, v_m \in \mathbb{R^n}$ to basis of the $\mathbb{R^n}$ using standard basis vectors $e_1, \ldot , \e_n$.

- Q: Find solutions to homogeneous system $Ax=0$, where $A \in \mathrm{M}_{mn}(\mathbb{R})$
A: TODO: <https://en.wikipedia.org/wiki/System_of_linear_equations#Homogeneous_systems>

Every homogeneous system has at least the zero solution.

If $\operatorname{rank}(A) = n$ then there is trivial solution only: $x = 0$. 
If $\operatorname{rank}(A) < n$ then there is a basis of $(n - \operatorname{rank}(A))$ linear independent solutions, general solution looks like $c_1 x^1 + \ldots + c_{n-r}x^{n-r}$. 

Example:

$$
A' = 
\begin{pmatrix}
{1}&{0}&{a_{31}}&{0}&{a_{51}}\\
{0}&{1}&{a_{32}}&{0}&{a_{52}}\\
{0}&{0}&{0}&{1}&{a_{53}}\\
\end{pmatrix}
$$

$u_1 = \begin{pmatrix}{-a_{51}}&{-a_{52}}&{0}&{-a_{53}}&{1}\end{pmatrix}$
$u_2 = \begin{pmatrix}{-a_{31}}&{-a_{32}}&{1}&{0}&{0}\end{pmatrix}$

- Q: Find basis in null space of matrix, i.e., ${x \vert Ax = 0}$.

- Q: Express a vector space as $V = \langle v_1, \ldots ,v_m \rangle$, where $v_i \in \mathbb{R^n}$

# Questions

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- linear algebra -- algorithms">
    <p>Your browser does not support iframes.</p>
</iframe>
