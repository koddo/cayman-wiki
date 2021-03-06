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

## Minimal polynomial

<https://en.wikipedia.org/wiki/Minimal_polynomial_(linear_algebra)>

Miminal polynomial is a polynomial of the least degree that $P(A) = 0$. It looks similar to characteristic polynomial, they have the same roots, the eigenvalues. But the multiplicities are different.

> The multiplicity of a root $\lambda$ of $\mu_A$ is the largest power $m$ such that $Ker(A − \lambda E)^m$ strictly contains $Ker(A − \lambda E)^{m−1}$. In other words, increasing the exponent up to $m$ will give ever larger kernels, but further increasing the exponent beyond $m$ will just give the same kernel. 

Minimal polynomial of a square matrix divides its characteristic polynomial, see Cayley–Hamilton theorem.

<https://math.stackexchange.com/questions/81467/when-are-minimal-and-characteristic-polynomials-the-same>

# Jordan normal form

## JNF for complex matrices

<https://en.wikipedia.org/wiki/Jordan_normal_form#Complex_matrices>

- Algebraic multiplicity — sum of sizes of Jordan blocks for eigenvalues
- Geometric multiplicity — number of blocks for an eigenvalue, aka dimension of eigenspace
- Multiplicity in minimal polynomial — size of the biggest block

Number of blocks of size $\ge j$ is $\operatorname{dim} \operatorname{Ker}(A - λE)^j - \operatorname{dim} \operatorname{Ker}(A - λE)^{j-1}$
For Size $= j$ it is $2 \operatorname{dim} ker (A - λE)^j - \operatorname{dim} ker (A - λE)^{j+1} - \operatorname{dim} ker (A - λE)^{j-1}$

## JNF for real matrices

<https://en.wikipedia.org/wiki/Jordan_normal_form#Real_matrices>

# Cayley–Hamilton theorem

$p(\lambda) = \det(A - \lambda E)$ — characteristic polynomial. The Cayley–Hamilton theorem states that substituting the matrix $A$ for $\lambda$ results in the zero matrix: $p(A) = 0$ 

Equivalently, (when the ring is a field) the Cayley–Hamilton theorem states that the minimal polynomial of a square matrix divides its characteristic polynomial: <https://math.stackexchange.com/questions/1097548/the-minimal-polynomial-divides-the-characteristic-polynomial>

<https://en.wikipedia.org/wiki/Cayley–Hamilton_theorem>

# Superlearn

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- linear algebra -- eigenvalues and eigenvectors">
    <p>Your browser does not support iframes.</p>
</iframe>

