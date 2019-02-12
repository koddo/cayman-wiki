---
title:  "Linear algebra algorithms"
layout: default

---

* this line gets replaced with the generated table of contents
{:toc}


# In a set of vectors $v_1, \ldots, v_m \in \mathbb{R^n}$ find a basis and express others as linear combinations. Find some basis in a span $V = \langle v_1, \ldots ,v_m \rangle$, where $v_i \in \mathbb{R}$.

SL-

To find some basis, put vectors in matrix horizontally and get reduced row echelon form.

To find out what vectors in a set form a basis and express others a linear combination, put them in matrix vertically and get row echelon form.

# Extend a set of linear independent vectors $v_1, \ldots, v_m \in \mathbb{R^n}$ to basis of the $\mathbb{R^n}$ using standard basis vectors $e_1, \ldots , e_n$.

SL-

Put them in matrix horizontally and get reduced row echelon form.
<https://math.stackexchange.com/questions/465870/how-to-extend-a-basis>

# Find solutions of homogeneous system $Ax=0$, where $A \in \mathrm{M}_{mn}(\mathbb{R})$

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

## Relation to nonhomogeneous systems

$Ax = b$
$Ax = 0$

Let's say $p$ is a solution to the first one: $Ap = b$.
Then the entire solution set is $\{p + v \vert Av = 0\}$, because $A(p+v) = Ap + Av = b$

# Find basis in null space of matrix, i.e., ${x \vert Ax = 0}$



# Express a vector space $V = \langle v_1, \ldots ,v_m \rangle, \  v_i \in \mathbb{R^n}$ as matrix equation $Ax = 0$. I.e., $V = \{ x \vert Ax = 0 \}$ 



# Change of basis for vector and for matrix.


# Check if there's a basis in which operator $\phi$ is represented as diagonal matrix

SS- SL-

<https://en.wikipedia.org/wiki/Diagonalizable_matrix>
<file:///Users/alex/Dropbox/hse_math/linear_algebra 07 -- Seminar7.pdf#page=3>
<https://math.stackexchange.com/questions/1469461/finding-the-basis-b-of-the-matrix-t-in-which-b-is-diagonal-i-think-ive-got-it>
<https://math.stackexchange.com/questions/293172/linear-algebra-eigenvalues-and-diagonalizable-matrix>

# Find sum and intersection of vetror subspaces $V = \langle v_1,\ldots,v_m\rangle$, $U = \langle u_1,\ldots,u_k\rangle$, where $v_i, u_j\in \mathbb{R^n}$



# Find sum and intersection of vetror subspaces when they are expressed as matrix equations.

$U = \{ x \vert Ax = 0 \}$, $U = \{ x \vert Bx = 0 \}$
$U \cap V = \{ x \vert Ax = 0\,, Bx = 0 \}$
$C' = \left(\frac{A}{B}\right)$
Find linear linear independent set of vectors in $C'$, this is the matrix $C$ we need.

# Find projection of a vector onto a subspace along another subspace, projection operator onto subspace along another subspace



# Find out if there is a linear operator $\phi\colon V\to U$ such that $\phi(v_i) = u_i$



# Find basis of image and basis of kernel of linear map



# Change of basis of bilinear form

$(f_1,\ldots,f_n) = (e_1,\ldots,e_n)C$

$B' = C^T B C$

# Polarization of quadratic form.

# Find left and right orthogonal complements to subspace.

# Diagonilize a quadratic form. Find it's signature. Find it's signature using principal minors method. Silvester's criterion.
<https://en.wikipedia.org/wiki/Sylvester%27s_criterion>
<file:///Users/alex/Disk.Yandex/DISK/Алгебра.by_Винберг.pdf#page=210>

# Gram–Schmidt process.

# Find operator of orthoprojection. Find orthoprojection of vector on subspace.

# Find eigenvalues and eigenvectors.

# Find value of parallelepiped $v_1, \ldots, v_k$.
A: Find linear independent subset, get $\det G$, determinant of Gram matrix $G = (v_i, v_j)$.

# Find angle between vectors. Find angle and distance between vector and subspace.

# Reduced SVD for horizontally oriented matrices. What if an eigenvalue is zero? Are eigenvalues used once in \Lambda or repeated if their degree is not one? How to get SVD of vertically oriented matrices?
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

If an eigenvalue is zero, we ignore it. Eigenvalues $\sqrt{\sigma_i}$ are repeated $n_i$ times in $\Lambda$.

For each $\sigma_i$ orthogonalize and normalize basis of $(S - \sigma_i E) x = 0$, lets call them $v_1^i, \ldots, v_{n_i}^i$ (check yourself that their number is the degree $n_i$ of eigenvalue). Put these bases into columns of the $C$ matrix.

Solve $D^T = \Lambda^{-1} C^T A$.

For vertically oriented matrices get SVD for horizonally $A^T$, which is $A^T = C \Lambda D^T$, then $A = D \Lambda^T C^T$.

# Questions

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- linear algebra -- algorithms">
    <p>Your browser does not support iframes.</p>
</iframe>
