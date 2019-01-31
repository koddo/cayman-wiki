---
title:  "Linear algebra algorithms"
layout: default

---

* this line gets replaced with the generated table of contents
{:toc}

# ?

- Q: In a set of vectors $v_1, \ldots, v_m \in \mathbb{R^n}$ find a basis and express others as linear combinations.
A: 

- Q: Find some basis in a span $V = \langle v_1, \ldots ,v_m \rangle$, where $v_i \in \mathbb{R}$.

- Q: Extend a set of linear independent vectors $v_1, \ldots, v_m \in \mathbb{R^n}$ to basis of the $\mathbb{R^n}$ using standard basis vectors $e_1, \ldots , e_n$.

- Q: Find solutions of homogeneous system $Ax=0$, where $A \in \mathrm{M}_{mn}(\mathbb{R})$.
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

- Q: Express a vector space $V = \langle v_1, \ldots ,v_m \rangle, \  v_i \in \mathbb{R^n}$ as matrix equation $Ax = 0$. I.e., $V = \{ x \vert Ax = 0 \}$. 

- Q: Change of basis for vector and for matrix.

- Q: Find sum and intersection of vetror subspaces $V = \langle v_1,\ldots,v_m\rangle$, $U = \langle u_1,\ldots,u_k\rangle$, where $v_i, u_j\in \mathbb{R^n}$.
Find sum and intersection of vetror subspaces when they are expressed as matrix equations.

- Q: Find projection of a vector on a subspace along another subspace.
Find projection operator on subspace along another subspace.

- Q: Find out if there is a linear operator $\phi\colon V\to U$ such that $\phi(v_i) = u_i$.

- Q: Find basis of image and basis of kernel of linear map.

- Q: Change of basis of bilinear form.

- Q: Polarization of quadratic form.

- Q: Find left and right orthogonal complements to subspace.

- Q: Diagonilize a quadratic form. Find it's signature. Find it's signature using principal minors method. Silvester's criterion.
<https://en.wikipedia.org/wiki/Sylvester%27s_criterion>
<file:///Users/alex/Disk.Yandex/DISK/Алгебра.by_Винберг.pdf#page=210>

- Q: Gram–Schmidt process.

- Q: Find operator of orthoprojection. Find orthoprojection of vector on subspace.

- Q: Find eigenvalues and eigenvectors.

- Q: Find value of parallelepiped $v_1, \ldots, v_k$.
A: Find linear independent subset, get $\det G$, determinant of Gram matrix $G = (v_i, v_j)$.

- Q: Find angle between vectors. Find angle and distance between vector and subspace.

- Q: Reduced SVD for horizontally oriented matrices. How to get SVD of vertically oriented matrices?
A:
$A = C \Lambda D^T$, but we only get reduced matrices.

Find eigenvalues of $S = AA^T = C \Lambda^2 C^T$, they are $\sigma_1, ..., \sigma_k$, their degrees are $n_1, \ldots, n_k$.

$$
\Lambda = 
\begin{pmatrix}
{\sqrt{\sigma_1}}&{}&{}\\
{}&{\ddots}&{}\\
{}&{}&{\sqrt{\sigma_k}}
\end{pmatrix}
$$

For each $\sigma_i$ orthogonalize and normalize basis of $(S - \sigma_i E) x = 0$, lets call them $v_1^i, \ldots, v_{n_i}^i$ (check yourself that their number is the degree $n_i$ of eigenvalue). Put these bases into columns of the $C$ matrix.

Solve $D^T = \Lambda^{-1} C^T A$.

For vertically oriented matrices get SVD for horizonally $A^T$, which is $A^T = C \Lambda D^T$, then $A = D \Lambda^T C^T$.

# Questions

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- linear algebra -- algorithms">
    <p>Your browser does not support iframes.</p>
</iframe>
