---
title:  "Linear algebra -- eigenvalues and eigenvectors"
layout: default

---

* this line gets replaced with the generated table of contents
{:toc}

# Eigenvalues and eigenvectors

Eigenvectors of real symmetric matrices are orthogonal: <https://math.stackexchange.com/questions/82467/eigenvectors-of-real-symmetric-matrices-are-orthogonal>:
$<\langle A\mathbf{x},\mathbf{y}\rangle = \langle\mathbf{x},A^T\mathbf{y}\rangle>$
$\lambda\langle\mathbf{x},\mathbf{y}\rangle = \langle\lambda\mathbf{x},\mathbf{y}\rangle = \langle A\mathbf{x},\mathbf{y}\rangle = \langle\mathbf{x},A^T\mathbf{y}\rangle = \langle\mathbf{x},A\mathbf{y}\rangle = \langle\mathbf{x},\mu\mathbf{y}\rangle = \mu\langle\mathbf{x},\mathbf{y}\rangle$

Eigenvalues of block matrix $M$ are eigenvalues of $A$ and $D$ combined, <https://math.stackexchange.com/questions/207865/the-eigenvalues-of-a-block-matrix>, <https://math.stackexchange.com/questions/21454/prove-that-the-eigenvalues-of-a-block-matrix-are-the-combined-eigenvalues-of-its>:

$$
M = 
\begin{pmatrix} 
A & B \\
0 & D
\end{pmatrix}
$$

How many distinct possible forms for its Jordan canonical matrix are there for 4x4 non-diagonalizable matrix with two unique eigenvalues?
The answer is 4 non-equivalent configurations.
24 is a wrong answer: <https://math.stackexchange.com/questions/1247574/how-many-distinct-possible-forms-for-its-jordan-canonical-matrix-are-there-4x4>

# Jordan normal form

## JNF for complex matrices

<https://en.wikipedia.org/wiki/Jordan_normal_form#Complex_matrices>

- Алгебраическая кратность — сумма размеров жордановых клеток для с.з.
- Геометрическая — количество клеток для с.з., она же — размерность собственного подпространства.
- Есть еще кратность корня в минимальном многочлене — размер самой большой клетки.

количество клеток размера >= j равно dim Ker(A - λE)^j - dim Ker(A - λE)^{j-1}
Ровно j: 2 dim ker (A - λE)^j - dim ker (A - λE)^{j+1} - dim ker (A - λE)^{j-1}

## JNF for real matrices

<https://en.wikipedia.org/wiki/Jordan_normal_form#Real_matrices>


# Superlearn

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- linear algebra -- eigenvalues and eigenvectors">
    <p>Your browser does not support iframes.</p>
</iframe>

