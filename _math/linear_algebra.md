---
title:  "Linear algebra"
layout: default

---

# TODOs

reverse of 2x2 matrix `d & -b \\ -c & a`

<https://en.wikipedia.org/wiki/Adjugate_matrix>

Лемма о фальшивом разложении определителя 


# test

When \\(a \ne 0\\), $a \ne 0$, there are two solutions to \\(ax^2 + bx + c = 0\\) and they are

$$x = {-b \pm \sqrt{\textcolor{red}{b^2-4ac}} \over 2a}$$

\\[x = {-b \pm \sqrt{b^2-4ac} \over \textcolor{red}{2a}}\\]

# Systems of linear equations 


## Gaussian elimination

Elementary row operations are used to reduce a matrix to what is called triangular form.
Row switching, row multiplication, row addition.
These don't change the solution set.

<http://en.wikipedia.org/wiki/Elementary_matrix>

$$
T_{i,j} = \begin{bmatrix} 1 & & & & & & & \\ & \ddots & & & & & & \\ & & 0 & & 1 & & \\ & & & \ddots & & & & \\ & & 1 & & 0 & & \\ & & & & & & \ddots & \\ & & & & & & & 1\end{bmatrix}\quad 
$$

$$
T_i(m) = \begin{bmatrix} 1 & & & & & & \\ & \ddots & & & & & \\ & & 1 & & & & \\ & & & m & & & \\ & & & & 1 & & \\ & & & & & \ddots & \\ & & & & & & 1\end{bmatrix}\quad 
$$

$$
T_{i,j}(m) = \begin{bmatrix} 1 & & & & & & & \\ & \ddots & & & & & & \\ & & 1 & & & & & \\ & & & \ddots & & & & \\ & & m & & 1 & & \\ & & & & & & \ddots & \\ & & & & & & & 1\end{bmatrix}
$$


Elementary row operations do not change the solution set:

$\boxed{\Rightarrow}$ let $x: \ Ax=0 \quad \Leftrightarrow \quad E \cdot Ax = E \cdot 0$,  
then $(EA)x=0$,  
then $x$ is in null set of $EA$

$\boxed{\Leftarrow}$ let $x: \ EAx=0$,  
then $Ax = (E^{-1}E)Ax = E^{-1} (EA)x = E^{-1} 0 = 0$,  
then $x$ is in null set of $A$

But they change the image, see what happens after row switching:

$$A  = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 0 \end{pmatrix}$$

$$A' = \begin{pmatrix} 0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix}$$

A new matrix represents a projection to completely another plane.



Elementary row operations do not change the kernel of a matrix (and hence do not change the solution set), but they do change the image.

Dually, elementary column operations do not change the image, but they do change the kernel.

## Gauss-Jordan elimination vs Gaussian elimination

Usually one use Gauss-Jordan to invert a matrix and Gaussian for rank.

Both are $O(n^3)$ for an $n$ by $n$ full rank matrix, but order of magnitude of Gauss-Jordan elimination is $n^3$, whereas that for Gaussian elimination is $\frac{2}{3}n^3$


Row echelon form --- result of Gaussian elimination:

$$
\left( \begin{array}{ccccc}
1 & a_0 & a_1 & a_2 & a_3 \\
0 & 0 & 1 & a_4 & a_5 \\
0 & 0 & 0 & 1 & a_6
\end{array} \right)
$$


Reduced row echelon form --- result of Gauss-Jordan elimination:

$$ 
\left( \begin{array}{ccccc}
1 & 0 & 0 & 0 & b_1 \\
0 & 1 & 0 & 0 & b_2 \\
0 & 0 & 0 & 1 & b_3
\end{array} \right)
$$

and

$$
\begin{pmatrix}
1 & 0 & -2 & 3 & 0 & -24 \\
0 & 1 & -2 & 2 & 0 & -7 \\
0 & 0 & 0 & 0 & 1 & 4
\end{pmatrix}
$$


TODO LOW: <http://cstheory.stackexchange.com/questions/3921/what-is-the-actual-time-complexity-of-gaussian-elimination>


# Block matrices

<https://en.wikipedia.org/wiki/Block_matrix>

## Elementary row operations

блочное преобразование матриц

элементарные преобразования столбцов
(или строк)

Умножение на следующее:
E -B
0 E
$$
\begin{pmatrix}
E & -B \\
0 & E
\end{pmatrix}
$$
есть преобразования строк.

справа -- столбцов


# Problems

<https://www.dropbox.com/home/hse_math?preview=linear_algebra+01+--+Seminar1_problems.pdf>

- Q: hw1p4
- Q: hw1p8 -- only the idea?
- Q: hw1p9
- Q: hw1p14
- Q: hw1p15
- Q: The following two matrices:

$$
\begin{pmatrix}
{0}&{1}&{}&{}&{}\\
{}&{0}&{1}&{}&{}\\
{}&{}&{0}&{\ddots}&{}\\
{}&{}&{}&{\ddots}&{1}\\
{}&{}&{}&{}&{0}\\
\end{pmatrix}
$$

$$
\begin{pmatrix}
{0}&{1}&{}&{}&{}\\
{}&{0}&{1}&{}&{}\\
{}&{}&{0}&{\ddots}&{}\\
{}&{}&{}&{\ddots}&{1}\\
{1}&{}&{}&{}&{0}\\
\end{pmatrix}
$$

- Q: Multiplication by blocks

$$
\begin{matrix}
{}&{
\begin{matrix}
{k}&{s}
\end{matrix}}\\
{
\begin{matrix}
{m}\\
{n}
\end{matrix}}&{
\begin{pmatrix}
{A}&{B}\\
{C}&{D}
\end{pmatrix}}
\end{matrix}
\quad\quad
\begin{matrix}
{}&{
\begin{matrix}
{u}&{v}
\end{matrix}}\\
{
\begin{matrix}
{k}\\
{s}
\end{matrix}}&{
\begin{pmatrix}
{X}&{Y}\\
{W}&{Z}
\end{pmatrix}}
\end{matrix}
$$

$$
\begin{matrix}
{}&{
u\quad\quad\quad\quad\quad v
}\\
{
\begin{matrix}
{m}\\
{n}
\end{matrix}}&{
\begin{pmatrix}
{A X + B W}&{A Y + B Z}\\
{C X + D W}&{C Y + D Z}
\end{pmatrix}}
\end{matrix}
$$

Example:

$$
\begin{pmatrix}
{A}&{v}\\
{0}&{\lambda}
\end{pmatrix}
\begin{pmatrix}
{A}&{v}\\
{0}&{\lambda}
\end{pmatrix}
=
\begin{pmatrix}
{A^2}&{Av + v\lambda}\\
{0}&{\lambda^2}
\end{pmatrix}
=
\begin{pmatrix}
{A^2}&{Av + \lambda v}\\
{0}&{\lambda^2}
\end{pmatrix}
=
\begin{pmatrix}
{A^2}&{(A + \lambda E) v}\\
{0}&{\lambda^2}
\end{pmatrix}
$$

- Q: Good properties of matrix operations: all those associativity, commutativity, distributivity of addition and multiplication by scalars. And bad properties: non-commutativity, null divisors, some matrices taken to powers even give zero:

$$
\begin{pmatrix}
{0}&{1}\\
{0}&{0}
\end{pmatrix}
\begin{pmatrix}
{0}&{0}\\
{1}&{0}
\end{pmatrix}
=
\begin{pmatrix}
{1}&{0}\\
{0}&{0}
\end{pmatrix}\quad\text{но}\quad
\begin{pmatrix}
{0}&{0}\\
{1}&{0}
\end{pmatrix}
\begin{pmatrix}
{0}&{1}\\
{0}&{0}
\end{pmatrix}
=\begin{pmatrix}
{0}&{0}\\
{0}&{1}
\end{pmatrix}
$$

$$
\begin{pmatrix}
{1}&{0}\\
{0}&{0}
\end{pmatrix}
\begin{pmatrix}
{0}&{0}\\
{0}&{1}
\end{pmatrix}
=0
$$

$\exists A \quad A^n = 0$:

$$
\begin{pmatrix}
{0}&{1}\\
{0}&{0}
\end{pmatrix}
\begin{pmatrix}
{0}&{1}\\
{0}&{0}
\end{pmatrix}
=0
$$



- Q: 
$$
\det\begin{pmatrix}
1 & -1 & 2 & -1 \\
0 &  1 & 0 &  2 \\
3 & -1 & 4 & -1 \\
0 &  3 & 0 &  4
\end{pmatrix}
$$


# bilinear forms with char(F) not equal 2
    
bilinear function is a generalization of vector dot product 
main purpose of bilinear theory is to make matrix simpler by choosing a good basis, so it's good to know properties that do not depend on basis: kernel, etc
   

bilinear function $\alpha: V \times V \mapsto F$ is linear in each of its arguments


everywhere it is assumed that $\operatorname{char}(F) \neq 2$
   
   
## characteristic of field
    
TODO: what is characteristic of F? http://ru.wikipedia.org/wiki/Характеристика_кольца, 

if exists, the characteristic $\operatorname{char}(R)$ is the smallest $n$ such that $\forall r \ : \ nr =0$ 
   
if doesn't exist, then $\operatorname{char}(R) = 0$
when $\operatorname{char}(R) = 1$, the ring is trivial set: {0, 1}

    
$\operatorname{char} \mathbb{Z} = \operatorname{char} \mathbb{Q} = \operatorname{char} \mathbb{R} = 0$

$\operatorname{char} \mathbb{Z}_n = n$

$\operatorname{char}(\mathbb{F}_{p^m}) = p$

    
TODO: why characteristic of GF(p^m)=p?


## dim of kernel of bilinear form

$\ker\alpha = \left\{ y : \alpha(x,y) = 0 \right\}$
     
     
$\ker\alpha = \left\{ y \ : \  \alpha(e_i,y) = 0, \ i = 1, \ldots, n \right\}$
this gives a system of linear equations, which matrix is $A$ 
then
$\operatorname{dim}\ker\alpha = n - \operatorname{rank} A$


     
## examples of bilinear forms
  
example. vector dot product is a bilinear function
example. $\alpha (f, g) = \int_a^b f(x)g(x)dx$ is a bilinear function in $C[a,b]$
    
TODO: add more examples of bilinear forms

    
## matrix representation of bilinear form

$x = \sum x_i e_i$, $y = \sum y_j e_j$

$$\alpha(x,y) = \sum_{i,j} \alpha_{ij} x_i y_j$$, where $a_{ij} = \alpha(e_i, e_j)$

$A = (a_{ij})$ is matrix representation in basis $\{e_1, \ldots, e_n \}$

$\alpha(x, y) = X^\top A \  Y$, where X and Y are rows of coordinates
   

in a given basis each bilinear map can be uniquely represented by a matrix

$$
\alpha(x,y)=\begin{pmatrix}x_1 & x_2 & \ldots & x_n \end{pmatrix}\begin{pmatrix} \alpha(e_1, e_1) & \alpha(e_1, e_2) & \ldots & \alpha(e_1, e_n) \\ \alpha(e_2, e_1) & \alpha(e_2, e_2) & \ldots & \alpha(e_2, e_n) \\ \vdots & \vdots & \ddots & \vdots \\ \alpha(e_n, e_1) & \alpha(e_n, e_2) & \ldots & \alpha(e_n, e_n) \end{pmatrix}\begin{pmatrix}y_1 \\ y_2 \\ \vdots \\ y_n \end{pmatrix}
$$
   
     
## examples of matrices of bilinear forms
  
$f : F^3 \mapsto F$
$f (x, y) = x_1 y_2 + x_1 y_3 - 2 x_3 y_1$ 

$a_{11} = f ( < 1, 0, 0 > , < 1, 0, 0 > ) = 1 \cdot 0 + 1 \cdot 0 - 2 \cdot 0 \cdot 1 = 0$ 
$a_{12} = f ( < 1, 0, 0 > , < 0, 1, 0 > ) = 1 \cdot 1 + 1 \cdot 0 - 2 \cdot 0 \cdot 0 = 1$ 
$a_{12} = f ( < 1, 0, 0 > , < 0, 0, 1 > ) = 1 \cdot 0 + 1 \cdot 1 - 2 \cdot 0 \cdot 0 = 1$ 
$\ldots$
$a_{31} = f ( < 0, 0, 1 > , < 1, 0, 0 > ) = 0 \cdot 0 + 0 \cdot 1 - 2 \cdot 1 \cdot 1 = 2$
$\ldots$
$a_{33} = f ( < 0, 0, 1 > , < 0, 0, 1 > ) = 0 \cdot 0 + 0 \cdot 1 - 2 \cdot 1 \cdot 0 = 0$
     
$$f(x,y) \ = \  
\begin{pmatrix} x_1 & x_2 & x_3 \end{pmatrix}^\top
\
\begin{pmatrix}
0 & 1 & 1 \\
0 & 0 & 0 \\
-2 & 0 & 0
\end{pmatrix}
\ \ 
\begin{pmatrix} y_1 \\ y_2 \\ y_3 \end{pmatrix}
\ = \ x_1 y_2 + x_1 y_3 - 2 x_3 y_1
$$
     
## change of basis
  
$(e'_1, \ldots, e'_n) = (e_1, \ldots, e_n) \cdot C$
$X = CX'$, $Y = CY'$
$\alpha(x, y) = (CX')^\top \ A \  (CY') = (X')^\top C^\top A \  C \  Y'$
then in new basis $A = C^\top A \  C$




   
## symmetric and skew-symmetric bilinear forms
  
symmetric: $\alpha(y, x) = \alpha(x, y)$
skew-symmetric: $\alpha(y, x) = - \alpha(x, y)$
there are also non-symmetric and non-skew-symmetric bilinear functions

bilinear function is symmetric $\iff$ $A^\top = A$
bilinear function is skew-symmetric $\iff$ $A^\top = - A$

this property is independent of basis

    

symmetric matrix:
$$
\begin{pmatrix}
i & 2 & 3 \\
2 & j & 4 \\
3 & 4 & k
\end{pmatrix}
$$
    
skew-symmetric matrix always have zeros on its diagonal:
$$
\begin{pmatrix}
0 & 2 & 3 \\
-2 & 0 & 4 \\
-3 & -4 & 0
\end{pmatrix}
$$

    

Theorem:
if $\operatorname{char}(F) \neq 2$, then vector space of all bilinear forms is direct sum of subspaces: of symmetric bilinear forms and skew-symmetric bilinear forms
Proof:
if $\alpha$ is symmetric and skew-symmetric simultaneously, then $\alpha(x, y) = \alpha(y, x) = - \alpha(x, y) \ \Rightarrow \ 2\alpha(x, y) = 0 \ \Rightarrow \ \alpha(x, y) = 0$
    
i.e. every bilinear form can be represented as a sum of symmetric and skew-symmetric bilinear forms:
$\alpha(x,y) \  = \  \frac{1}{2}\left\{ \alpha(x,y) + \alpha(y,x) \right\} \  + \  \frac{1}{2}\left\{ \alpha(x,y) - \alpha(y,x) \right\}$
or in for their matrices: $A \ = \  \frac{1}{2}(A + A^\top) \ + \  \frac{1}{2}(A - A^\top)$   
    
    
    
but if $\operatorname{char}(F) = 2$ the theorem does not work:
$F = \{0, 1\}$,  then a skew-symmetric form is the same as a symmetric form: $\alpha(-1, x) = - \alpha(1, x) = \alpha(1, x)$ 
and, for example, $\begin{pmatrix}0 & 1 \\ 0 & 1\end{pmatrix}$ can't be represented as a sum of two symmetric matrices
    
TODO: do i need alternating forms which are f(v,v) = 0?
If the characteristic of F is not 2 then the converse is also true: every skew-symmetric form is alternating. 
If, however, char(F) = 2 then a skew-symmetric form is the same as a symmetric form and there exist alternating forms which are not symmetric/skew-symmetric.
A bilinear form is alternating if and only if its coordinate matrix is skew-symmetric and the diagonal entries are all zero (which follows from skew-symmetry when char(F) ≠ 2).

    
    
    
TODO: in bilinear forms section, what if $\operatorname{char} F = 2$ +? https://docs.google.com/a/egotv.ru/viewer?a=v&q=cache:2cBYrJa0egoJ:www.math.uregina.ca/~bailey/pjc60/slides/JIHtalk.pdf+&hl=en&gl=ru&pid=bl&srcid=ADGEESiFkiK-RE_grFgDgATUbJigqZNg55FUUXogfSgVP5uy1H2ONLVOwNkV_F-DME8oZlYc8aakE46cDwGcaUamOKz39EEZYkQRbswF7-J-NPotAv4bf6Bc2OCHaeRtsxAEIHtNPZ3j&sig=AHIEtbTQgPTST7GrVjPGu_XgwEySzql5Vw
                 

