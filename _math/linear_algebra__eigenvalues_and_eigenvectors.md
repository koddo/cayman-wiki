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


# Superlearn

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- linear algebra -- eigenvalues and eigenvectors">
    <p>Your browser does not support iframes.</p>
</iframe>

