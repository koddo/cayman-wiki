---
title:  "Linear algebra -- matrices"
layout: default

---

* this line gets replaced with the generated table of contents
{:toc}

# Symmetric matrices

Sum and difference of symmetric matrices are symmetric, while product is symmetric if and only if matrices commute: $AB = BA$.
Consequence: for symmetric $A$ the $A^n$ is also symmetric.

When $A^{-1}$ exists, it is symmetric if and only if $A$ is symmetric.

Any square matrix can uniquely be written as sum of a symmetric and a skew-symmetric matrix: $X = \frac{1}{2} \left( X+X^T \right) + \frac{1}{2} \left( X-X^{T} \right)$

Real $A$ is symmetric if and only if $\langle Ax,y\rangle =\langle x,Ay\rangle \quad \forall x,y\in {\mathbb {R}}^{n}$.
Because $\langle Ax,y\rangle = (Ax)^T y = x^T A^T y = x^T Ay = <x, Ay>$.
<https://math.stackexchange.com/questions/410905/symmetric-matrix-and-inner-product-langle-ah-x-rangle-langle-h-at-x-rangl>

Real symmetric matrices that commute can be simultaneously diagonalized:
there exists a basis such that every element of the basis is an eigenvector for both $A$ and $B$.
<https://math.stackexchange.com/questions/236212/simultaneously-diagonalizable-proof>
<https://math.stackexchange.com/questions/56307/simultaneous-diagonalization>

After orthogonal change of basis ($CC^T=1$) symmetric matrix stays symmetric: $(C^{-1} S C)^T = C^T S^T (C^{-1})^T = C^{-1} S C$.

# Orthogonal matrix.

<https://en.wikipedia.org/wiki/Orthogonal_matrix>

An orthogonal matrix is a square matrix whose columns and rows are orthogonal unit vectors (i.e., orthonormal vectors):
$Q^{\mathrm {T} }Q=QQ^{\mathrm {T} }=I$
${\displaystyle Q^{\mathrm {T} }=Q^{-1}}$

Orthogonal matrices preserve dot product: ${\displaystyle {\mathbf {v} }^{\mathrm {T} }{\mathbf {v} }=(Q{\mathbf {v} })^{\mathrm {T} }(Q{\mathbf {v} })={\mathbf {v} }^{\mathrm {T} }Q^{\mathrm {T} }Q{\mathbf {v} }}$

# Superlearn

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- linear algebra -- matrices">
    <p>Your browser does not support iframes.</p>
</iframe>


