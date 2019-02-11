---
title:  "Linear algebra"
layout: default

---

* this line gets replaced with the generated table of contents
{:toc}

# TODO

reverse of 2x2 matrix `d & -b \\ -c & a`

<https://en.wikipedia.org/wiki/Adjugate_matrix>

Лемма о фальшивом разложении определителя 

<https://en.wikipedia.org/wiki/Gramian_matrix>

<https://ru.wikipedia.org/wiki/Сопряжённый_оператор>, <https://en.wikipedia.org/wiki/Hermitian_adjoint>


Я правильно понимаю, что между билинейными формами и двойственными пространствами тоже есть связь?
Да, связь есть. Главный факт такой: если есть билинейная форма  b: V x U -> R, то она дает два линейных отображения V -> U^* по правилу v -> b(v, -) и U -> V^* по правилу u -> b( -, u). Если билинейная форма не вырождена (у нее нет левого и правого ядер), то эти отображения являются изоморфизмами (в некотором смысле естественными). В частном случае скалярного произведения (-,-) : V x V -> R это дает изоморфизм V -> V^* по правилу v -> (v, -). То есть любая линейная функция на Евклидовом пространстве -- это скалярное произведение с некоторым вектором.


По поводу задач на двойственные пространства.
Можно глянуть в Кострикина следующие задачи: 36.9-36.17, 36.19, 36.20. Можно и 36.18 поглядеть, но там надо догадаться до ответа.
Для 36.9 и 36.10 понадобится определение сопряженного базиса. Базис e_1,...,e_n из V и базис f_1,...,f_n из V^* сопряжены, если верно: f_i(e_j) = 1, если i = j и f_i(e_j)  = 0, если i != j.



Есть принцип двойственности для векторных пространств. О соответствии различных характеристик у V и V^*. Если тебе интересно, то можешь поглядеть на мои задачи для очников прошлого года на эту тему. Их можно найти тут:  https://yadi.sk/d/rWjfAGc33N9gsX
Смотреть надо на семинар 15 задача 10 и семинар 18 задачи: 6,7 и 8.
Задачи эти не то чтобы сильно простые. 
Простые задачи я постараюсь подобрать из Кострикина. Но это не сегодня.
На квадратичные формы в Кострикине тоже есть задачи. Можно просто открыть раздел на квадратичные формы и попытать начать решать по-порядку. Но я как буду подбирать задачи на двойственное пространство, загляну и туда. Постараюсь завтра это сделать вместе с подбором домашнего задания по новой теме.


set of invertible matrices is open and dense
Где-то прочитал, что важно всегда помнить, что множество обратимых матриц открыто и плотно.
Да, я про это рассказывал, когда объяснял принцип продолжения по непрерывности. Даже набирал листочек по поводу метода решения задач этим принципом. Он есть среди материалов курса.


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


# Solution set of Homogeneous systems
    
$$
\left\{\begin{array}{ccc}
a_{11}x_1+\ldots+a_{1n}x_n &=& 0 \\
\ldots & & \\
a_{m1}x_1+\ldots+a_{mn}x_n &=& 0
\end{array}\right.
\iff A_{m\times n} \ \vec{x}=\vec{0},\quad A_{m\times n}=\left(\begin{array}{ccc}a_{11} & \ldots & a_{1n}\\ \ldots & & \\ a_{m1} & \ldots & a_{mn}
\end{array}\right)
$$

Every homogeneous system has at least the zero solution.

if $\operatorname{rank}(A) = n$ then there is only trivial solution: $\vec{x} = \vec{0}$ 
if $\operatorname{rank}(A) < n$ then there is a basis of $(n - \operatorname{rank}(A))$ linear independent solutions, general solution looks like $c_1\vec{x}^1+\ldots+c_{n-r}\vec{x}^{n-r}$ 
    
http://ru.wikipedia.org/wiki/Решение_систем_линейных_алгебраических_уравнений


if $x_1$, $x_2$ are solutions for $Ax=0$
then $x_1 + x_2$ is solution for the homogenous system $Ax=0$
$A (x_1 + x_2) = 0 - 0 = 0$
    
    
TODO: proof of theorem about solution set of homogeneous system of linear equations

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

$\ker\alpha = { y : \alpha(x,y) = 0 }$
     
$\ker\alpha = { y \ : \  \alpha(e_i,y) = 0, \ i = 1, \ldots, n }$
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
$\alpha(x,y) \  = \  \frac{1}{2}{ \alpha(x,y) + \alpha(y,x) } \  + \  \frac{1}{2}{ \alpha(x,y) - \alpha(y,x) }$
or in for their matrices: $A \ = \  \frac{1}{2}(A + A^\top) \ + \  \frac{1}{2}(A - A^\top)$
    
    
    
but if $\operatorname{char}(F) = 2$ the theorem does not work:
$F = \{0, 1\}$,  then a skew-symmetric form is the same as a symmetric form: $\alpha(-1, x) = - \alpha(1, x) = \alpha(1, x)$ 
and, for example, $\begin{pmatrix}0 & 1 \\ 0 & 1\end{pmatrix}$ can't be represented as a sum of two symmetric matrices
    
TODO: do i need alternating forms which are f(v,v) = 0?
If the characteristic of F is not 2 then the converse is also true: every skew-symmetric form is alternating. 
If, however, char(F) = 2 then a skew-symmetric form is the same as a symmetric form and there exist alternating forms which are not symmetric/skew-symmetric.
A bilinear form is alternating if and only if its coordinate matrix is skew-symmetric and the diagonal entries are all zero (which follows from skew-symmetry when char(F) ≠ 2).

    
    
    
TODO: in bilinear forms section, what if $\operatorname{char} F = 2$ +? https://docs.google.com/a/egotv.ru/viewer?a=v&q=cache:2cBYrJa0egoJ:www.math.uregina.ca/~bailey/pjc60/slides/JIHtalk.pdf+&hl=en&gl=ru&pid=bl&srcid=ADGEESiFkiK-RE_grFgDgATUbJigqZNg55FUUXogfSgVP5uy1H2ONLVOwNkV_F-DME8oZlYc8aakE46cDwGcaUamOKz39EEZYkQRbswF7-J-NPotAv4bf6Bc2OCHaeRtsxAEIHtNPZ3j&sig=AHIEtbTQgPTST7GrVjPGu_XgwEySzql5Vw
                 



# Quadratic forms
   
$q(x) = \sum a_{ij} \, x_i x_j \ : \ V \mapsto F$
$A = (a_{ij})$ is the symmetric matrix of the quadratic form

the matrix is symmetric when $\operatorname{char} F \neq 2$

examples:
$$
\begin{aligned}
x^2 - 4xy + y^2 + 5xz + 2yz + z^2 \ &= \  x^2 - 2xy -2yx + y^2 + \frac{5}{2}xz + \frac{5}{2}zx + yz + zy + z^2 \ = \\
&= \left(\begin{array}{ccc} x & y & z\end{array}\right) \left(\begin{array}{ccc}1 & -2 & \frac{5}{2} \\ -2 & 1 & 1 \\ \frac{5}{2} & 1 & 1\end{array}\right)\left(\begin{array}{ccc} x \\ y \\ z\end{array}\right)
\end{aligned}
$$

$$
ax^2+bxy+cy^2 = \left(\begin{array}{ccc} x & y \end{array}\right) \left(\begin{array}{ccc} a & \frac{b}{2} \\ \frac{b}{2} & c\end{array}\right)\left(\begin{array}{ccc} x \\ y \end{array}\right)
$$
   

any symmetric bilinear form b defines a quadratic form: $q(x) = \alpha(x,x)$
   
we can restore the bilinear function, this is called a polarization of a quadratic form: $\alpha(x,y)=\frac{1}{2}{q(x+y)-q(x)-q(y)} = x^\mathrm{T}Ay = y^\mathrm{T}Ax$
this is from $\alpha(x+y, x+y) = q(x) + q(y) + 2\alpha(x,y)$
these two processes are the inverses of one another $\alpha(x, -x)=\frac{1}{2}{q(0)-q(x)-q(-x)}$ $\Leftrightarrow$ $q(x) = \alpha(x,x) + \frac{1}{2}q(0)$. Substitute $x=0$ and get $q(0) = 0$, then $q(x) = \alpha(x,x)$
   
   
matrix of a polar bilinear form is equal to matrix of quadratic form
as a consequence, when $\operatorname{char} F \neq 2$, the theories of symmetric bilinear forms and of quadratic forms in n variables are essentially the same
   

## orthogonal complement

$\operatorname{char} F \neq 2$
$\alpha(x, y)$ is a symmetric or skew-symmetric bilinear form
$x$ and $y$ are /orthogonal/ if $\alpha(x, y) = 0$
when bilinear form is skew-symmetric, every vector is orthogonal to itself

the orthogonal complement of a subspace $W$ of a vector space $V$ equipped with a bilinear form is the set $W^\bot$ of all vectors in $V$ that are orthogonal to every vector in $W$
$W^\bot = {x\in V \  : \  \forall y\in W \ \alpha(x, y) = 0 }$

$V^\bot = \operatorname{Ker}\alpha$

if $\alpha(x, y) \not\equiv 0$, then $\dim W + \dim {W^\bot} = \dim V$ 
and $(W^\bot)^\bot = W$

    
## orthogonal basis for symmetric bilinear form

A basis is orthogonal with respect to the bilinear function when basis vectors are mutually orthogonal
When $\operatorname{char} F \neq 2$, for a symmetric bilinear form there is always an orthogonal basis
a basis is orthogonal $\iff$ the matrix representation is a diagonal matrix, then bilinear and quadratic function look like this: $\alpha(x, y) = a_1 x_1 y_1 + \ldots + a_n x_n y_n$, $q(x) = a_1 x_1^2 + \ldots + a_n x_n^2$
       
    
### Gram–Schmidt process --- orthonormalising a set of vectors

$$\mathrm{proj}_{\mathbf{b}}\,\mathbf{a} = {\langle \mathbf{b}, \mathbf{a}\rangle\over\langle \mathbf{b}, \mathbf{b}\rangle}\mathbf{b}$$
     
$$
\begin{align*}
\mathbf{b}_1 & = \mathbf{a}_1, & \mathbf{e}_1 & = {\mathbf{b}_1 \over \|\mathbf{b}_1\|} \\
\mathbf{b}_2 & = \mathbf{a}_2-\mathrm{proj}_{\mathbf{b}_1}\,\mathbf{a}_2,
& \mathbf{e}_2 & = {\mathbf{b}_2 \over \|\mathbf{b}_2\|} \\
\mathbf{b}_3 & = \mathbf{a}_3- \left( \mathrm{proj}_{\mathbf{b}_1}\,\mathbf{a}_3+\mathrm{proj}_{\mathbf{b}_2}\,\mathbf{a}_3 \right), & \mathbf{e}_3 & = {\mathbf{b}_3 \over \|\mathbf{b}_3\|} \\
\mathbf{b}_4 & = \mathbf{a}_4- \left( \mathrm{proj}_{\mathbf{b}_1}\,\mathbf{a}_4+\mathrm{proj}_{\mathbf{b}_2}\,\mathbf{a}_4+\mathrm{proj}_{\mathbf{b}_3}\,\mathbf{a}_4 \right), & \mathbf{e}_4 & = {\mathbf{b}_4 \over \|\mathbf{b}_4\|} \\
& {}\ \  \vdots & & {}\ \  \vdots \\
\mathbf{b}_k & = \mathbf{a}_k-\sum_{j=1}^{k-1}\mathrm{proj}_{\mathbf{b}_j}\,\mathbf{a}_k, & \mathbf{e}_k & = {\mathbf{b}_k\over \|\mathbf{b}_k \|}.
\end{align*}
$$

$\mathbf{b}_1$ and $\mathbf{b}_2$ are orthogonal:
$$\langle\mathbf{b}_1, \mathbf{b}_2\rangle = \langle\mathbf{b}_1, \mathbf{a}_2-\mathrm{proj}_{\mathbf{b}_1}\,\mathbf{a}_2\rangle = \langle\mathbf{b}_1, \mathbf{a}_2\rangle - \langle\mathbf{b}_1, \mathrm{proj}_{\mathbf{b}_1}\,\mathbf{a}_2\rangle = \langle\mathbf{b}_1, \mathbf{a}_2\rangle - \langle\mathbf{b}_1, {\langle \mathbf{b}_1, \mathbf{a}_2\rangle\over\langle \mathbf{b}_1, \mathbf{b}_1\rangle} \mathbf{b}_1 \rangle = \langle\mathbf{b}_1, \mathbf{a}_2\rangle - {\langle \mathbf{b}_1, \mathbf{a}_2\rangle\over\langle \mathbf{b}_1, \mathbf{b}_1\rangle} \langle\mathbf{b}_1, \mathbf{b}_1 \rangle = 0$$ 
    
$\mathbf{b}_2$ and $\mathbf{b}_3$ are orthogonal similarly:
$$\langle\mathbf{b}_2, \mathbf{b}_3\rangle = \langle\mathbf{b}_2, \mathbf{a}_3- \left( \mathrm{proj}_{\mathbf{b}_1}\,\mathbf{a}_3+\mathrm{proj}_{\mathbf{b}_2}\,\mathbf{a}_3 \right)\rangle = \langle\mathbf{b}_2, \mathbf{a}_3\rangle - 0 - \langle\mathbf{b}_2, \mathrm{proj}_{\mathbf{b}_2}\,\mathbf{a}_3\rangle$$
    
etc
    
     
## canonical, or normal form of quadratic function

If $F = \mathbb C$, coefficients $\alpha_i = 0, 1$, i.e. canonical quadratic function look like $q(x) = x_1^2 + \ldots + x_r^2$ after a suitable permutation of basis vectors, $r = \operatorname{rank} q$.
    
If $F = \mathbb R$, coefficients $\alpha_i = -1, 0, 1$, i.e. canonical quadratic function look like $q(x) = x_1^2 + \ldots + x_k^2 - x_{k+1}^2 - \ldots - x_{k+l}^2$ after a suitable permutation of basis vectors.
$k+l = \operatorname{rank} q$

a pair $(k,l)$ is called signature of $q$
    
    
### law of inertia
   
$k$ and $l$ do not depend on a particular choice of diagonalizing basis

// it's about invariant signature, the word "inertia" was used because no better word was found
    
$k$ is max dimention of a subspace on which $q(x)$ is positive definite
(same for $l$)


TODO: proof of law of inertia


## positive definite and negative definite quadratic forms
  
$q(x) > 0$ for $x \neq 0$ is positive definite
$q(x) < 0$ for $x \neq 0$ is negative definite
    
bilinear form $\alpha(x, y)$ is positive definite if associated quadratic form $q(x)$ is positive definite (same for negative)
dot product $(x, y)$ of vectors is positive definite


normal form of positive definite quadratic function is $q(x) = x_1^2 + \ldots + x_k^2$


    
    
## Sylvester's criterion --- is a quadratic form positive definite
  
Sylvester's criterion states that a matrix $A$ is positive definite $\iff$ all the following matrices have a positive determinant:
the upper left 1-by-1 corner
the upper left 2-by-2 corner
...
the upper left n-by-n corner -- $A$ itself
    
$$A = \begin{pmatrix} a_{11} & a_{12} & \ldots & a_{1n} \\ a_{21} & a_{22} & \ldots & a_{2n} \\ \ldots & \ldots & \ldots & \ldots \\ a_{n1} & a_{n2} & \ldots & a_{nn} \end{pmatrix}$$
$$\Delta_1=a_{11}$$
$$\Delta_2=\begin{vmatrix}a_{11} & a_{12} \\ a_{21} & a_{22}\end{vmatrix}$$
$$\Delta_3=\begin{vmatrix}a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \\ a_{31} & a_{32} & a_{33}\end{vmatrix}$$
$$\Delta_i=\begin{vmatrix} a_{11} & a_{12} & \ldots & a_{1i} \\ a_{21} & a_{22} & \ldots & a_{2i} \\ \ldots & \ldots & \ldots & \ldots \\ a_{i1} & a_{i2} & \ldots & a_{ii}\end{vmatrix}$$
$$\Delta_n = |A|$$
    
    
in another words, all leading principal minors are positive
    

    
if every $\Delta_k$ is non-zero then the negative index of inertia is equal to the number of sign changes in the sequence $\Delta_0=1, \Delta_1, \ldots, \Delta_n=\det A$

    
    

TODO: do i need $F = Z_p$?

TODO: do i need skew-symmetric bilinear functions? symplectic basic?


# superlearn

- Q: <https://en.wikipedia.org/wiki/Lagrange_polynomial>
- Q: What is orthogonal matrix? Examples.
- Q: Gram–Schmidt orthogonalization.
TODO:
$$
\begin{aligned}
u_1 &= v_1
u_2 &= v_2 - \operatorname(proj)_{v_1}(v_2)
u_3 &= v_3 - \operatorname(proj)_{v_1}(v_3) - \operatorname(proj)_{v_2}(v_3)
&\cdots
\end{aligned}
$$
Discard zeroes.
<https://en.wikipedia.org/wiki/Gram%E2%80%93Schmidt_process>

- Q: Cauchy–Bunyakovsky–Schwarz inequality.
A: $|\langle \mathbf {u} ,\mathbf {v} \rangle |^{2}\leq \langle \mathbf {u} ,\mathbf {u} \rangle \cdot \langle \mathbf {v} ,\mathbf {v} \rangle$
TODO: proof <https://en.wikipedia.org/wiki/Cauchy%E2%80%93Schwarz_inequality>

- Q: Vandermonde matrix.
A: TODO: proof <https://en.wikipedia.org/wiki/Vandermonde_matrix>

- Q: Orthogonal matrix.
A: TODO: <https://en.wikipedia.org/wiki/Orthogonal_matrix>

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- linear algebra">
    <p>Your browser does not support iframes.</p>
</iframe>

- Q: Describe orthogonal matrices with integer numbers; with non-negative real numbers.
A: <http://sci.alnam.ru/book_alin.php?id=27>

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- linear algebra -- problems">
    <p>Your browser does not support iframes.</p>
</iframe>


definition of minor of matrix
a minor of a matrix A is the determinant of some smaller square matrix, cut down from A by removing one or more of its rows or columns<div><br /></div><div><br /></div><div>[$$]</div><div>\begin{vmatrix}</div><div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; \,\,1 &amp; 4 &amp; \Box\, &amp; \Box\, \\</div><div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; \,\Box &amp; \Box &amp; \Box\, &amp; \Box\, \\</div><div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -1 &amp; 9 &amp; \Box\, &amp; \Box\, \\</div><div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; \end{vmatrix}&nbsp;</div><div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; \longrightarrow</div><div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; \begin{vmatrix}</div><div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; \,\,\,1 &amp; 4\, \\</div><div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -1 &amp; 9\, \\</div><div>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; \end{vmatrix} = (9-(-4)) = 13</div><div>[/$$]</div>
algebra matrix minor


what are elementary operations in Gaussian elimination?
<div>row switching, row addition, row multiplication</div>
algebra gaussian_elimination systems_of_linear_equations

why in Gaussian elimination elementary row operations do not change solutions set?
see my notes
algebra gaussian_elimination systems_of_linear_equations

do elementary <i>row</i> operations in Gausian elimination change kernel and image?<div><br /></div><div>what about column operations?</div>
elementary <i>row</i> operations do not change the kernel (and hence do not change the solution set)<div><br /></div><div>they do change the image</div>
algebra gaussian_elimination systems_of_linear_equations

what is&nbsp;row echelon form?<div><br /></div><div>and what is <i>reduced</i> row echelon form?</div>
<div>row echelon form</div><div>[$$]<div>\left( \begin{array}{ccccc}</div><div>&nbsp; &nbsp;1 &amp; a_0 &amp; a_1 &amp; a_2 &amp; a_3 \\</div><div>&nbsp; &nbsp;0 &amp; 0 &amp; 1 &amp; a_4 &amp; a_5 \\</div><div>&nbsp; &nbsp;0 &amp; 0 &amp; 0 &amp; 1 &amp; a_6</div><div>&nbsp; &nbsp;\end{array} \right)</div>[/$$]</div><div><br /></div><div><br /></div><div><br /></div><div><i>reduced</i> row echelon form</div><div><div>[$$]<div>\left( \begin{array}{ccccc}</div><div>&nbsp; &nbsp;1 &amp; 0 &amp; 0 &amp; 0 &amp; b_1 \\</div><div>&nbsp; &nbsp;0 &amp; 1 &amp; 0 &amp; 0 &amp; b_2 \\</div><div>&nbsp; &nbsp;0 &amp; 0 &amp; 0 &amp; 1 &amp; b_3</div><div>&nbsp; &nbsp;\end{array} \right)</div>[/$$]</div></div><div><br /></div><div>[$$]\begin{pmatrix} 1 &amp; 0 &amp; -2 &amp; 3 &amp; 0 &amp; -24 \\ 0 &amp; 1 &amp; -2 &amp; 2 &amp; 0 &amp; -7 \\ 0 &amp; 0 &amp; 0 &amp; 0 &amp; 1 &amp; 4 \end{pmatrix}[/$$]</div>
algebra gaussian_elimination systems_of_linear_equations

what is time complexity of Gaussian elimination?
[$]O(n^3)[/$]<div><br /></div><div>TODO: why?</div>
algebra gaussian_elimination systems_of_linear_equations

<div>Let [$]V[/$] be a finite-dimensional vectorspace with a spanning set [$]S[/$] of [$]n[/$] vectors.</div><div>&nbsp; &nbsp;</div><div>Maximum number of linear independent vectors?</div>
<div><div><div><div>Every linear independent set in [$]V[/$] has a maximum of [$]n[/$] elements.</div></div></div></div>
algebra linear_independence

definition of rank of matrix
The column rank of a matrix A is the maximum number of linearly independent column vectors of A.<div><br /></div><div>[$]\iff[/$]</div><div><br /></div><div>The row rank is number of non-zero rows after Gaussian elimination.</div><div><br /></div><div>[$]\iff[/$]</div><div><br /></div><div>rank is largest size of a nonzero minor</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>row rank and&nbsp;column rank&nbsp;are always equal</div><div><br /></div>
algebra gaussian_elimination matrix rank

definition of basis
basis is a set of linearly independent vectors that, in a linear combination, can represent every vector in a given vector space
algebra basis vector_space

when&nbsp;a system of linear equations has a solution?<div><br /></div><div>criteria based on rank.</div>
<div>a system of linear equations with [$]n[/$] variables has a solution&nbsp;</div><div>[$]\Leftrightarrow[/$]</div><div>the rank of its coefficient matrix [$]A[/$] is equal to the rank of its augmented matrix [$][A|b][/$].</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>If n = rank(A), the solution is unique, otherwise there are infinite number of solutions.</div>
algebra matrix rank systems_of_linear_equations theorem

how many minors of size [$]k[/$] are there for a matrix of size [$]n \times m[/$]
[$]C_n^k \cdot C_m^k[/$]<div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>e.g. there are&nbsp;[$]C_3^2 \cdot C_3^2 = 9[/$] minors of size 2 for a 3x3 matrix</div><div>one for each of 9 elements of the matrix</div>
algebra matrix minor

definition of rank of matrix through minors and algorithm of counting
rank of A is the largest order of any non-zero minor in A<div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>brute force: if there is a non-zero minor of size 1 which is basically a non-zero element, then the rank is at least 1</div><div>then try all minors of size 2. If there is at least one non-zero minor, then the rank is at least 2.</div><div>after some steps, if we found that all minors of size k are zero, then the rank is k-1</div><div><br /></div><div><div><br /></div><div><br /></div><div>but there is an observation</div><div>&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;</div><div><div>&nbsp; &nbsp; Theorem. Suppose that there exists a minor [$]m_n[/$] of order [$]n[/$] for a matrix that is nonzero and such that all minors of order [$]n+1[/$] which contain [$]m_n[/$] are zero.</div><div>&nbsp; &nbsp; Then rank of the matrix is [$]n[/$].</div></div></div><div><br /></div><div><br /></div><div><br /></div><div><div>then the algorithm is as following</div><div>&nbsp; &nbsp; take a non-zero 1-minor (it can be upper left element of matrix)</div><div>&nbsp; &nbsp; if there is a non-zero 2-minor which contain 1-minor, take it and</div><div>&nbsp; &nbsp; check 3-minors</div><div>&nbsp; &nbsp; after some steps if all k+1-minors that contain a k-minor from previous step are zero then the rank is k</div></div>
algebra matrix minor rank

solution set of homogeneous system of linear equations
[$]<div>&nbsp; \left\{\begin{array}{ccc}<div>&nbsp; &nbsp;a_{11}x_1+\ldots+a_{1n}x_n &amp;=&amp; 0 \\</div><div>&nbsp; &nbsp;\ldots &amp; &amp; \\</div><div>&nbsp; &nbsp;a_{m1}x_1+\ldots+a_{mn}x_n &amp;=&amp; 0</div><div>&nbsp; &nbsp;\end{array}\right.</div><div>&nbsp; &nbsp;\iff A_{m\times n} \ \vec{x}=\vec{0},\quad A_{m\times n}=\left(\begin{array}{ccc}a_{11} &amp; \ldots &amp; a_{1n}\\ \ldots &amp; &amp; \\ a_{m1} &amp; \ldots &amp; a_{mn}</div>&nbsp; &nbsp;\end{array}\right)<div>[/$]</div></div><div><br /></div><div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;if [$]\operatorname{rank}(A) = n[/$] then there is only trivial solution: [$]\vec{x} = \vec{0}[/$]</div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;if [$]\operatorname{rank}(A) &lt; n[/$] then there is a basis of [$](n - \operatorname{rank}(A))[/$] linear independent solutions, general solution looks like [$]c_1\vec{x}^1+\ldots+c_{n-r}\vec{x}^{n-r}[/$]&nbsp;</div></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><div>The solution set to any homogeneous system of linear equations with n variables is a subspace of [$]F^n[/$].</div><div><br /></div><div>For example, the set of all vectors [$](x, y, z)[/$] satisfying the equations [$]x + 3y + 2z = 0[/$] and [$]2x - 4y + 5z = 0[/$] is a one-dimensional subspace of [$]\mathbb R^3[/$].</div></div>
algebra homogeneous_system matrix rank systems_of_linear_equations

determinant of a 2x2 matrix
"[$$]\begin{vmatrix} a &amp; b\\c &amp; d \end{vmatrix}=ad - bc[/$$]<div><br /></div><div><img src=""algebra.org.20120925-1424-506Xck.screenshot.png"" /></div><div><br /></div><div><br /></div><div><br /></div><div>proof:</div><div><img src=""algebra.org.20120926-0941-506KZS.screenshot.png"" /></div>"
algebra determinant matrix

determinant of a 3x3 matrix
"[$]\begin{vmatrix}a&amp;b&amp;c\\d&amp;e&amp;f\\g&amp;h&amp;i\end{vmatrix} = a\begin{vmatrix}e&amp;f\\h&amp;i\end{vmatrix}-b\begin{vmatrix}d&amp;f\\g&amp;i\end{vmatrix}+c\begin{vmatrix}d&amp;e\\g&amp;h\end{vmatrix} = aei+bfg+cdh-ceg-bdi-afh[/$]<div><br /></div><div><img src=""20130329-2018-4699Oqd.screenshot.png"" /></div><div><br /></div><div><img src=""algebra.org.20120925-1430-506xww.screenshot.png"" /></div><div><br /></div><div><br /></div><div><img src=""algebra.org.20120925-1424-506kmq.screenshot.png"" /></div>"
algebra determinant matrix

definition of determinant
by transpositions<div><br /></div><div>[$$]\Delta=\sum_{\alpha_1, \alpha_2, \ldots, \alpha_n} \operatorname{parity}(\alpha_1, \alpha_2, \ldots, \alpha_n) \ \ \cdot \ \ &nbsp;a_{\alpha_1 1} \cdot \ldots \cdot a_{\alpha_n n}[/$$]</div>
algebra determinant matrix

<div>determinant property</div><div><br /></div>[$]\det(A^{\rm T}) = \ ?[/$]
[$]\det(A^{\rm T}) = \det(A)[/$]
algebra determinant matrix

determinant property<div><br /></div><div>[$$]\det(A^{-1}) = \ ?[/$$]</div>
[$$]\det(A^{-1}) = \frac{1}{\det(A)}[/$$]
algebra determinant matrix

<div>determinant property</div><div><br /></div>[$]\det(AB) = \ ?[/$]
[$]\det(AB) = \det(A)\det(B)[/$]
algebra determinant matrix

determinant property<div><br /></div>[$$]\det(cA) = \ ?[/$$]
[$$]\det(cA) = c^n\det(A)[/$$]
algebra determinant matrix

determinant of triangular matrix
the product of the diagonal entries:<div><br /></div><div>[$$]\det(A) = &nbsp;a_{1,1} a_{2,2} \cdots a_{n,n} = \prod_{i=1}^n a_{i,i}[/$$]</div>
algebra determinant matrix

how does interchanging of two rows or columns affect the determinant?
it multiplies the determinant by -1
algebra determinant matrix

how does adding a column multiplied by a constant to another columnt affects the determinant?
"does not change<div><br /></div><div><br /></div><div><img src=""algebra.org.20120926-1100-39848N7Q.screenshot.png"" /></div>"
algebra determinant matrix

determinant is zero --- what about linear independence?
rows are linear dependent [$]\iff[/$] [$]\det A = 0[/$]
algebra determinant matrix

determinant expansion by minors
"<div>[$$]B = \begin{bmatrix} 1 &amp; 2 &amp; 3 \\ 4 &amp; 5 &amp; 6 \\ 7 &amp; 8 &amp; 9 \end{bmatrix}[/$$]</div><div><br /></div><div>[$$]|B| = 1 \cdot \begin{vmatrix} 5 &amp; 6 \\ 8 &amp; 9 \end{vmatrix} - 2 \cdot \begin{vmatrix} 4 &amp; 6 \\ 7 &amp; 9 \end{vmatrix} + 3 \cdot \begin{vmatrix} 4 &amp; 5 \\ 7 &amp; 8 \end{vmatrix} = 1 \cdot (-3) - 2 \cdot (-6) + 3 \cdot (-3) = 0[/$$]</div><div><br /></div><div>[$$]|B| = -2 \cdot \begin{vmatrix} 4 &amp; 6 \\ 7 &amp; 9 \end{vmatrix} + 5 \cdot \begin{vmatrix} 1 &amp; 3 \\ 7 &amp; 9 \end{vmatrix} - 8 \cdot \begin{vmatrix} 1 &amp; 3 \\ 4 &amp; 6 \end{vmatrix} = -2 \cdot (-6) + 5 \cdot (-12) - 8 \cdot (-6) = 0[/$$]</div><div>&nbsp; &nbsp;</div><div><br /></div><div><br /></div><div>[$$]\det(A) = \sum_{j=1}^n (-1)^{i+j} a_{i,j} M_{i,j} = \sum_{i=1}^n (-1)^{i+j} a_{i,j} M_{i,j}[/$$]</div><div><br /></div><div><br /></div><div><img src=""algebra.org.20121004-1059-39848olA.screenshot.png"" style=""max-width: 90%; "" /></div>"
algebra determinant matrix minor

property of determinant<div><br /></div><div>[$$]\det\begin{pmatrix}A&amp; 0\\ C&amp; D\end{pmatrix} = \ ?[/$$]</div><div><br /></div><div>[$$]\det\begin{pmatrix}A&amp; B\\ 0&amp; D\end{pmatrix} = \ ?[/$$]</div><div><br /></div><div><br /></div><div>where A and D are square matrices</div>
&nbsp; &nbsp;[$$]\det\begin{pmatrix}A&amp; 0\\ C&amp; D\end{pmatrix} = \det\begin{pmatrix}A&amp; B\\ 0&amp; D\end{pmatrix} = \det(A) \det(D)[/$$]
algebra determinant matrix

matrix operation property<div><br /></div><div>[$](A^T)^{-1} = \ ?[/$]</div>
[$](A^T)^{-1} = (A^{-1})^T[/$]
algebra matrix

matrix operation property<div><br /></div><div>[$](AB)^{-1} = \ ?[/$]</div>
[$](AB)^{-1} = B^{-1}A^{-1}[/$]
algebra matrix

properties of [$$]\operatorname{rank} AB[/$$]
[$$]\operatorname{rank} AB \leqslant \operatorname{min} \{ \operatorname{rank} A, \operatorname{rank} B \}[/$$]<div><br /></div><div><br /></div><div>[$]\operatorname{rank}(A) + \operatorname{rank}(B) - n \leq \operatorname{rank}(A B)[/$]</div><div><br /></div>
algebra matrix rank

inversion of matrix using minors
"<div>[$$]A^{-1} = \frac{1}{\det A}\cdot C^{T}[/$$]</div><div>&nbsp;&nbsp;</div><div><br /></div><div>[$$]C_{ij}=(-1)^{i+j} M_{ij}[/$$]</div><div><br /></div><div><br /></div><div><img src=""algebra.org.20121004-1059-39848olA.screenshot.png"" /></div>"
algebra matrix minor rank

inversion by Gauss-Jordan elimination
<div>[$$][A|I] \Rightarrow \dots \Rightarrow [I|A^{-1}][/$$]</div><div><br /></div><div><br /></div><div>&nbsp; [$$] A =&nbsp;</div><div>&nbsp; \begin{bmatrix}</div><div>&nbsp; 2 &amp; -1 &amp; 0 \\</div><div>&nbsp; -1 &amp; 2 &amp; -1 \\</div><div>&nbsp; 0 &amp; -1 &amp; 2</div><div>&nbsp; \end{bmatrix}[/$$]</div><div><br /></div><div><br /></div><div>&nbsp; [$$] [A|I] =&nbsp;</div><div>&nbsp; \begin{bmatrix}</div><div>&nbsp; 2 &amp; -1 &amp; 0 &amp; 1 &amp; 0 &amp; 0\\</div><div>&nbsp; -1 &amp; 2 &amp; -1 &amp; 0 &amp; 1 &amp; 0\\</div><div>&nbsp; 0 &amp; -1 &amp; 2 &amp; 0 &amp; 0 &amp; 1</div><div>&nbsp; \end{bmatrix}[/$$]</div><div><br /></div><div><br /></div><div>&nbsp; [$$] [ I A^{-1} ] =&nbsp;</div><div>&nbsp; \begin{bmatrix}</div><div>&nbsp; 1 &amp; 0 &amp; 0 &amp; \frac{3}{4} &amp; \frac{1}{2} &amp; \frac{1}{4}\\</div><div>&nbsp; 0 &amp; 1 &amp; 0 &amp; \frac{1}{2} &amp; 1 &amp; \frac{1}{2}\\</div><div>&nbsp; 0 &amp; 0 &amp; 1 &amp; \frac{1}{4} &amp; \frac{1}{2} &amp; \frac{3}{4}</div><div>&nbsp; \end{bmatrix}[/$$]</div>
algebra gaussian_elimination matrix

how many bases in n-dimensional vector space over [$]F_q[/$]?
<div>&nbsp; Basis set [$]B = \{b_1, \ldots, b_n\}[/$]</div><div><br /></div><div><br /></div><div>&nbsp; [$]b_1[/$] can be chosen from [$]V \ &nbsp;\setminus &lt;0&gt;[/$]</div><div>&nbsp; [$]b_2[/$] can be chosen from [$]V \ &nbsp;\setminus &lt;b_1&gt;[/$]</div><div>&nbsp; [$]b_3[/$] can be chosen from [$]V \ &nbsp;\setminus &lt;b_1, b_2&gt;[/$]</div><div>&nbsp; ...</div><div>&nbsp; [$]b_n[/$] can be chosen from [$]V \ &nbsp;\setminus &lt;b_1, b_2, \ldots, b_{n-1}&gt;[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><div><br /></div><div><br /></div><div>[$$](q^n-1)\cdot(q^n-q)\cdot \ldots \cdot(q^n-q^{n-1})[/$$]</div></div><div><br /></div>
algebra basis vector_space

how many k-dimensional subspaces of n-dimensional vector space over [$]F_q[/$]?
<div>choose k linear independent vectors:</div><div><br /></div><div><br /></div><div>Basis set [$]B = \{b_1, \ldots, b_n\}[/$]</div><div><br /></div><div>[$]b_1[/$] can be chosen from [$]V \ &nbsp;\setminus &lt;0&gt;[/$]</div><div>[$]b_2[/$] can be chosen from [$]V \ &nbsp;\setminus &lt;b_1&gt;[/$]</div><div>[$]b_3[/$] can be chosen from [$]V \ &nbsp;\setminus &lt;b_1, b_2&gt;[/$]</div><div>...</div><div>[$]b_k[/$] can be chosen from [$]V \ &nbsp;\setminus &lt;b_1, b_2, \ldots, b_{k-1}&gt;[/$]&nbsp;&nbsp;</div><div><br /></div><div><div>[$](q^n-1)(q^n-q) \ldots (q^n-q^{k-1})[/$]</div></div><div><br /></div><div><br /></div><div>subspaces they span may repeat --- we can get rid of this fact</div><div>how many bases in k-dimensional vector subspace?</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>[$$]\frac{(q^n-1)(q^n-q) \ldots (q^n-q^{k-1})}{(q^k-1)(q^k-q) \ldots (q^k-q^{k-1})}[/$$]</div><div><br /></div>
algebra basis vector_space

transformation matrix from one basis to another
[$$]C = \begin{pmatrix} c_{11} &amp; \dots &amp; \boldsymbol{c_{1j}} &amp;\dots &amp; c_{1n} &nbsp;\\ c_{21} &amp; \dots &amp; \boldsymbol{c_{2j}} &amp; \dots &amp; c_{2n} &nbsp;\\ &nbsp;\dots&amp;\dots&amp;\dots&amp;\dots&amp;\dots \\ c_{n1} &amp; \dots &amp; \boldsymbol{c_{nj}} &amp;\dots &amp; c_{nn} \end{pmatrix}[/$$]<div><br /></div><div><br /></div><div>[$$]e'_j \ = \ e_1 \, c_{1j} + e_2 \, c_{2j} + \ldots + e_n \, c_{nj} \ &nbsp;= \ \sum_k \, e_k \, c_{kj} \ &nbsp;= \ (e_1 \ \ldots \ e_n) \begin{pmatrix} c_{1j} \\ c_{2j} \\ \vdots \\ c_{nj} \end{pmatrix} [/$$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>[$$]x \ = \ (e_1 \ \ldots \ e_n) \begin{pmatrix} x_1 \\ \vdots \\ x_n \end{pmatrix} \ = \ (e'_1 \ \ldots \ e'_n) \begin{pmatrix} x'_1 \\ \vdots \\ x'_n \end{pmatrix} \ = \ (e_1 \ \ldots \ e_n) \cdot C \begin{pmatrix} x'_1 \\ \vdots \\ x'_n \end{pmatrix}[/$$]</div><div><br /></div><div><br /></div><div><br /></div><div>[$$]\begin{pmatrix} x'_1 \\ \vdots \\ x'_n \end{pmatrix} = C^{-1} \cdot \begin{pmatrix} x_1 \\ \vdots \\ x_n \end{pmatrix}[/$$]</div>
algebra basis matrix vector_space

definition of sum of vector subspaces
<div>[$]W_1+\ldots+W_n \ = \ &lt;W_1 \cup \ldots \cup W_n&gt;[/$]</div><div><br /></div><div>e.g., [$]R^3 = \text{x-axis} + \text{y-axis} + \text{z-axis}[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;</div><div>[$]\operatorname{dim} (U+W) = \operatorname{dim} U + \operatorname{dim} W - \operatorname{dim} (U \cap W)[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>representation [$]u = u_1 + \ldots + u_n[/$], [$]u_i \in U_i[/$] is unique [$]\iff[/$] the sum of subspaces is direct (that's one of definitions, see below)</div>
algebra vector_space

intersection of vector subspaces
is a subspace
algebra vector_space

definition of linear independence of vector subspaces
<div>collection of subspaces [$]U_1, \ldots, U_n[/$] is called linearly independent&nbsp;</div><div><br /></div><div>if [$]u_1 + \ldots + u_n = 0[/$]</div><div><br /></div><div>leads to [$]u_1 = \ldots = u_n = 0[/$]</div><div><br /></div><div>&nbsp; &nbsp;</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>for two subspaces U and W linear independence is equivalent to [$]U \cap W = 0[/$]</div><div><br /></div><div>for a bigger collection that is not true</div><div><br /></div>
algebra vector_space

definition of direct sum of subspaces
<div>[$]U_1 \oplus \ldots \oplus U_n[/$] is called a direct sum if it is a sum and subspaces are linearly independent</div><div><br /></div><div><br /></div><div><br /></div><div>equivalently, every vector has a unique representation [$]u = u_1 + \ldots + u_n[/$], [$]u_i \in U_i[/$]</div><div><br /></div><div>each [$]u_i[/$] is called a projection of [$]u[/$]</div><div><br /></div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;</div><div><br /></div><div>&nbsp; &nbsp;</div><div>direct sum decompositions are not unique</div><div>[$]R^2 = \text{x-axis} \oplus \text{y-axis} = \ &lt;(1,1)&gt; \oplus &lt;(1,2)&gt;[/$]</div>
algebra vector_space

what is the basis of a direct sum of vector subspaces?
the basis for a direct sum is the disjoint union of bases for the summands
algebra vector_space

definition of homomorphism
<div>&nbsp; &nbsp;homomorphism from a structure [$](G, *)[/$] to [$](H, \times)[/$] is a function [$]f(g_1 * g_2) = f(g_1) \times f(g_2)[/$]</div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;</div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;When an algebraic structure includes more than one operation, homomorphisms are required to preserve each operation.</div><div><br /></div><div>&nbsp; &nbsp;[$]f: (G, +, \times) \mapsto (H, \oplus, \otimes)[/$]</div><div><br /></div><div>&nbsp; &nbsp;[$]f(g_1 + g_2) = f(g_1) \oplus f(g_2)[/$]</div><div><br /></div><div>&nbsp; &nbsp;[$]f(g_1 \times g_2) = f(g_1) \otimes f(g_2)[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div>
algebra

definition of linear map
<div>[$]X[/$] and [$]Y[/$] are vector spaces over F</div><div>&nbsp;&nbsp;</div><div><br /></div><div><br /></div><div>linear map is a homomorphism [$]\varphi: X \mapsto Y[/$]</div><div>&nbsp;&nbsp;</div><div>[$]f(\mathbf{x}+\mathbf{y}) = f(\mathbf{x})+f(\mathbf{y})[/$]</div><div><br /></div><div>[$]f(\alpha \mathbf{x}) = \alpha f(\mathbf{x})[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp;&nbsp;</div><div>&nbsp;&nbsp;</div><div><br /></div><div>[$]\iff[/$]</div><div><br /></div><div>&nbsp; [$]f(\alpha \mathbf{x} + \beta \mathbf{y}) = \alpha f(\mathbf{x}) + \beta f(\mathbf{y})[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>instead of isomorphism, linear map does not require bijection</div>
algebra linear_map vector_space

definition of linear functional (linear form)
linear map from [$]V[/$] to [$]F[/$] &nbsp;is called a linear functional<div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>any linear functional can be written as [$]\varphi(x) = a_1 x_1 + \ldots + a_n x_n[/$], because&nbsp;</div><div><br /></div><div>[$]\varphi(x) = \varphi(x_1 e_1) + \ldots + \varphi(x_n e_n) = x_1 \varphi(e_1) + \ldots + x_n \varphi(e_n)[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>a&nbsp;hyperplane can be written using linear functional as [$]h(v) = b[/$]</div>
algebra linear_map vector_space

examples of linear map
<div><div>&nbsp; rotation is a liner map (and even isomorphism)</div><div><br /></div><div><br /></div><div>&nbsp; orthogonal projection of [$]E^3[/$] to a plane is a linear map (but not an isomorphism). [$]\ker\varphi[/$] is a line that is orthogonal to the plane</div><div><br /></div><div><br /></div><div>&nbsp; differentiation is a linear map from the space of all differentiable functions to the space of all functions</div><div><br /></div><div>&nbsp;&nbsp;</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; [$]x\mapsto x^2[/$] is not linear</div><div><br /></div><div><br /></div><div>&nbsp; [$]x\mapsto x+1[/$] is not linear (but is an affine transformation, and also a linear function, as defined in analytic geometry)</div></div><div><br /></div>
algebra example linear_map vector_space

when are vector spaces isomorphic?
<div>&nbsp; &nbsp;[$]V[/$] and [$]U[/$] are isomorphic [$]\iff[/$] [$]\operatorname{dim} V = \operatorname{dim} U[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;[$]\forall V[/$] over [$]F[/$] with [$]\operatorname{dim} V = n[/$] is isomorphic to [$]F^n[/$]</div><div><br /></div>
algebra vector_space

matrix representation of linear map
<div>&nbsp; &nbsp;linear map [$]\varphi: F^n \mapsto F^m[/$]</div><div><br /></div><div>&nbsp; &nbsp;[$]\{ e_1 \ \ldots \ e_n \}[/$] and [$]\{ f_1 \ \ldots \ f_m \}[/$] are given bases</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><div>&nbsp; [$$]\varphi(e_j) \ = \ f_1 \, a_{1j} + f_2 \, a_{2j} + \ldots + f_m \, a_{mj} \ &nbsp;= \ \sum_k \, f_k \, a_{kj} \ &nbsp;= \ (f_1 \ \ldots \ f_m) \begin{pmatrix} a_{1j} \\ a_{2j} \\ \vdots \\ a_{mj} \end{pmatrix} [/$$] &nbsp;&nbsp;</div><div><br /></div><div><br /></div><div>&nbsp; [$$]x \ = \begin{pmatrix} x_1 \\ \vdots \\ x_{\boldsymbol n} \end{pmatrix}[/$$], &nbsp; &nbsp; [$$]\varphi(x) = y = \begin{pmatrix} y_1 \\ \vdots \\ y_{\boldsymbol m} \end{pmatrix} = \begin{pmatrix} a_{11} &amp; \dots &amp; \boldsymbol{a_{1j}} &amp;\dots &amp; a_{1n} &nbsp;\\ a_{21} &amp; \dots &amp; \boldsymbol{a_{2j}} &amp; \dots &amp; a_{2n} &nbsp;\\ &nbsp;\dots&amp;\dots&amp;\dots&amp;\dots&amp;\dots \\ a_{m1} &amp; \dots &amp; \boldsymbol{a_{mj}} &amp;\dots &amp; a_{mn} \end{pmatrix} \cdot \begin{pmatrix} x_1 \\ \vdots \\ x_{\boldsymbol n} \end{pmatrix}[/$$]</div></div><div><br /></div><div><br /></div><div><br /></div><div>thus, there is a one-to-one correspondence between linear maps and matrices</div>
algebra linear_map matrix vector_space

definition of linear operator
"the expression ""linear operator"" is commonly used for a linear map from a vector space to itself (i.e., endomorphism)"
algebra linear_map vector_space

definition of kernel
<div>&nbsp; &nbsp;[$]\ker\varphi=\{x \ : \ &nbsp;\varphi(x)=0 \}[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;by definition [$]\ker(A)[/$] of the matrix is the solution space to [$]Ax=0[/$]</div><div><br /></div><div><br /></div><div>[$]\dim\ker\varphi \ &nbsp;= &nbsp;\ n - \operatorname{rk} A[/$]</div>
algebra kernel linear_map matrix

definition of image
"[$]\operatorname{im}(f)=\{y \ : \ &nbsp;y=f(x) \}[/$]<div><br /></div><div><br /></div><div><br /></div><div><img src=""algebra.org.20121021-1757-12518yvs.screenshot.png"" /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>[$]\dim\operatorname{im}\varphi = \operatorname{rk}A[/$]</div><div><br /></div><div>where&nbsp;[$]\varphi : F^n \mapsto F^m[/$] --- linear map with matrix [$]A[/$]</div>"
algebra image linear_map

relation between dimentions of kernel and image
<div>[$]\dim \ker \varphi \ + \ &nbsp;\dim \operatorname{im} \varphi \ = \ &nbsp;\dim X[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div>[$]\varphi: X \mapsto Y[/$]<div><br /></div><div><br /></div><div><br /></div><div><div>[$]\ker\varphi[/$] is a subspace of [$]X[/$]</div><div><br /></div><div>[$]\operatorname{im}\varphi[/$] &nbsp;is a subspace of [$]Y[/$]</div></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><div>example. a projection of 3d space to 2d plane (x,y,z) -&gt; (x,y) --- kernel is a vertical line through center, image is 2d plane itself</div><div><br /></div><div>example. nonzero linear function [$]\varphi : F^n \mapsto F[/$], then [$]\operatorname{im}\varphi = F[/$] and [$]\dim\ker\varphi = n - 1[/$]</div></div>
algebra image kernel linear_map

definition of dual space
<div>&nbsp; &nbsp;dual vector space [$]V^*[/$] --- set of all linear functionals on [$]V[/$]</div><div><br /></div><div>&nbsp; &nbsp;[$]V^*[/$] becomes a vector space over [$]F[/$] when equipped with the following&nbsp;</div><div><br /></div><div>&nbsp; &nbsp;[$](\varphi + \psi)(x) = \varphi(x) + \psi(x)[/$]</div><div><br /></div><div>&nbsp; &nbsp;[$](a \varphi)(x) = a \left(\varphi(x)\right)[/$]</div><div>&nbsp; &nbsp;</div><div><br /></div>
algebra dual_space linear_map vector_space

examples of linear functional (linear form)
<div>&nbsp; &nbsp;example. [$]\alpha(x) = (a, x)[/$] --- dot product of vectors --- is a linear functional&nbsp;</div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;example. [$]\alpha(f) = f'(x_0)[/$] is a linear functional on vector space of differentiable functions</div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;example. [$]I(f) = \int_a^b f(x) \, dx[/$] is a linear functional on vector space [$]C[a,b][/$] of continous functions</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><div>example. differentiation is a linear operator in the space of polynomials of degree [$]\leqslant n[/$]</div><div>&nbsp;&nbsp;</div><div>&nbsp;in basis [$]\{1, x, x^2, x^3, \ldots, x^n \}[/$] has a matrix</div><div><br /></div><div>&nbsp; &nbsp;[$$]</div><div>&nbsp; &nbsp;\begin{pmatrix}</div><div>&nbsp; &nbsp;0 &amp; 1 &amp; &nbsp; &amp; &nbsp; &amp; \cdots &amp; &nbsp; \\</div><div>&nbsp; &nbsp; &nbsp;&amp; 0 &amp; 2 &amp; &nbsp; &amp; \cdots &amp; &nbsp; \\</div><div>&nbsp; &nbsp; &nbsp;&amp; &nbsp; &amp; 0 &amp; 3 &amp; \cdots &amp; &nbsp; \\</div><div>&nbsp; &nbsp; &nbsp;&amp; &nbsp; &amp; &nbsp; &amp; &nbsp; &amp; \ddots &amp; &nbsp; \\</div><div>&nbsp; &nbsp; &nbsp;&amp; &nbsp; &amp; &nbsp; &amp; &nbsp; &amp; \cdots &amp; n \\</div><div>&nbsp; &nbsp; &nbsp;&amp; &nbsp; &amp; &nbsp; &amp; &nbsp; &amp; \cdots &amp; 0 \\</div><div>&nbsp; &nbsp;\end{pmatrix}</div><div>&nbsp; &nbsp;[/$$]</div><div>&nbsp; &nbsp;</div><div><br /></div><div>&nbsp; &nbsp;in basis [$]\{ 1, \frac{x}{1!}, \frac{x^2}{2!}, \frac{x^3}{3!}, \ldots, \frac{x^n}{n!} \}[/$]</div><div><br /></div><div>&nbsp; &nbsp;[$$]</div><div>&nbsp; &nbsp;\begin{pmatrix}</div><div>&nbsp; &nbsp;0 &amp; 1 &amp; &nbsp; &amp; &nbsp; &amp; \cdots &amp; &nbsp; \\</div><div>&nbsp; &nbsp; &nbsp;&amp; 0 &amp; 1 &amp; &nbsp; &amp; \cdots &amp; &nbsp; \\</div><div>&nbsp; &nbsp; &nbsp;&amp; &nbsp; &amp; 0 &amp; 1 &amp; \cdots &amp; &nbsp; \\</div><div>&nbsp; &nbsp; &nbsp;&amp; &nbsp; &amp; &nbsp; &amp; &nbsp; &amp; \ddots &amp; &nbsp; \\</div><div>&nbsp; &nbsp; &nbsp;&amp; &nbsp; &amp; &nbsp; &amp; &nbsp; &amp; \cdots &amp; 1 \\</div><div>&nbsp; &nbsp; &nbsp;&amp; &nbsp; &amp; &nbsp; &amp; &nbsp; &amp; \cdots &amp; 0 \\</div><div>&nbsp; &nbsp;\end{pmatrix}</div><div>&nbsp; &nbsp;[/$$]</div></div>
algebra dual_space linear_map vector_space

isomorphism of a vector space and it's dual space
<div>&nbsp; &nbsp;[$]V \cong V^* \iff \operatorname{dim} V = \operatorname{dim} V^*[/$] because dual basis has the same number of vectors:</div><div><br /></div><div>&nbsp; &nbsp;[$]\{ e_1, \ldots, e_n \}[/$] --- basis in [$]V[/$], [$]x = \sum x_i \, e_i[/$]</div><div><br /></div><div>&nbsp; &nbsp;[$]\{ \varepsilon_1, \ldots, \varepsilon_n \}[/$] --- [$]\varepsilon_i(x) = x_i[/$] --- dual basis in [$]V^*[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;or equivalently [$$]\varepsilon_i(e_j) = \delta_{ij} = \begin{cases} 1, &amp; \text{if } i = j \\ 0, &amp; \text{if } i \ne j \end{cases}[/$$] --- Kronecker delta symbol&nbsp;</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;this isomorphism [$]A : V \mapsto V^*[/$] is /not canonical/ because when we change basis in [$]V[/$], the dual basis in [$]V^*[/$] also changes, so there are as many isomorphisms as bases</div><div><br /></div><div><br /></div><div><br /></div><div>if [$]V[/$] Euclidean space --- it has dot product [$](x, y)[/$] --- there is canonical isomorphism between [$]V[/$] and [$]V^*[/$]: [$]x \mapsto f_x(t) = (x, t)[/$]</div>
algebra dual_space linear_map vector_space

isomorphism of a vector space and it's double dual space
<div>[$]V \cong V^{**}[/$] --- there exists isomorphism --- /canonical/ in that sence that it does not depend on basis:</div><div><br /></div><div>&nbsp; &nbsp;[$]A : V \mapsto V^{**}[/$]</div><div><br /></div><div>&nbsp; &nbsp;[$]A(x) = A_x[/$], where [$]A_x(f) = f(x)[/$]</div><div><br /></div><div>&nbsp; &nbsp;linearity: [$]A(\alpha x + \beta y) = A_{\alpha x + \beta y} = \alpha A_x + \beta A_y = \alpha A(x) + \beta A(y)[/$]</div><div><br /></div><div>&nbsp; &nbsp;bijection: [$]\{ e_1, \ldots, e_n \}[/$], [$]\{ \varepsilon_1, \ldots, \varepsilon_n \}[/$], [$]\{ A_{e_1}, \ldots, &nbsp;A_{e_n} \}[/$] --- basises in [$]V[/$], [$]V^*[/$], and [$]V^{**}[/$], where [$]A_{e_i}(\varepsilon_j) = \varepsilon_j(e_i) = \delta_{ij}[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;[$]V[/$] and [$]V^*[/$] are dual for each other since we can consider [$]x \in V[/$] as linear function [$]A_x(f)[/$]</div>
algebra dual_space linear_map vector_space

matrix of linear operator and transformation matrix from one basis to another
<div>linear operator [$]\mathcal A: V \mapsto V[/$]</div><div><br /></div><div>&nbsp; &nbsp;in basis [$]\{e_1, \ldots, e_n \}[/$] matrix [$]A[/$] of linear operator [$]\mathcal A[/$]</div><div><br /></div><div>[$]\mathcal A e_j = \sum_i e_i \, a_{ij}[/$]</div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;[$$]\{ \mathcal A e_1, \ldots, \boldsymbol{\mathcal A e_j}, \ldots, \mathcal A e_n \} \ &nbsp;= \ &nbsp; (e_1, \ldots, e_n) \cdot A \ &nbsp;= \ &nbsp; (e_1, \ldots, e_n) \begin{pmatrix} a_{11} &amp; \dots &amp; \boldsymbol{a_{1j}} &amp;\dots &amp; a_{1n} &nbsp;\\ a_{21} &amp; \dots &amp; \boldsymbol{a_{2j}} &amp; \dots &amp; a_{2n} &nbsp;\\ &nbsp;\dots&amp;\dots&amp;\dots&amp;\dots&amp;\dots \\ a_{n1} &amp; \dots &amp; \boldsymbol{a_{nj}} &amp;\dots &amp; a_{nn} \end{pmatrix}[/$$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;</div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;let [$]C[/$] be a transition matrix from basis [$]\{e_1, \ldots, e_n \}[/$] to basis [$]\{e'_1, \ldots, e'_n \}[/$]:</div><div><br /></div><div>&nbsp; &nbsp;[$](e'_1, \ldots, e'_n) = (e_1, \ldots, e_n) \cdot C[/$]</div><div><br /></div><div>&nbsp; &nbsp;[$](e'_1, \ldots, e'_n) \cdot A' = (\mathcal A e'_1, \ldots, \mathcal A e'_n) = (\mathcal A e_1, \ldots, \mathcal A e_n) \cdot C = (e_1, \ldots, e_n) \cdot AC = (e'_1, \ldots, e'_n) \cdot C^{-1}AC[/$]</div><div><br /></div><div>&nbsp; &nbsp;[$]A' = C^{-1}AC[/$]</div>
algebra linear_map vector_space

examples of linear operators
"<div>rotation &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [$]\mathbf{A}=\begin{pmatrix}\cos(\theta) &amp; -\sin(\theta)\\ \sin(\theta) &amp; \cos(\theta)\end{pmatrix}[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;reflection</div><div>&nbsp; &nbsp;scaling</div><div>&nbsp; &nbsp;projection</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;horizontal shear &nbsp; &nbsp;&nbsp; &nbsp;</div><div><br /></div><div>[$]\mathbf{A}=\begin{pmatrix}1 &amp; m\\ 0 &amp; 1\end{pmatrix}[/$]</div><div><img src=""20130403-1640-4699ane.screenshot.png"" /></div>"
algebra linear_map vector_space

definition of bilinear form
bilinear function [$]\alpha: V \times V \mapsto F[/$] is linear in each of its arguments<div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; bilinear function is a generalization of vector dot product&nbsp;</div><div><br /></div>
algebra bilinear_form

examples of bilinear forms
<div>&nbsp; example. vector dot product is a bilinear function</div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; example. [$]\alpha (f, g) = \int_a^b f(x)g(x)dx[/$] is a bilinear function in [$]C[a,b][/$]</div><div><br /></div>
algebra bilinear_form

matrix representation of bilinear form
see my notes
algebra bilinear_form

matrix of bilinear form after change of basis
<div>[$](e'_1, \ldots, e'_n) = (e_1, \ldots, e_n) \cdot C[/$]</div><div><br /></div><div>&nbsp; [$]X = CX'[/$]</div><div><br /></div><div>[$]Y = CY'[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; [$]\alpha(x, y) = (CX')^\top \ A \ &nbsp;(CY')&nbsp;= (X')^\top C^\top A \ &nbsp;C \ &nbsp;Y'[/$]</div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp;&nbsp;</div><div><br /></div><div>then in new basis [$]A = C^\top A \ &nbsp;C[/$]</div>
algebra bilinear_form

definition of symmetric and skew-symmetric bilinear forms
<div>&nbsp; &nbsp;symmetric: [$]\alpha(y, x) = \alpha(x, y)[/$]</div><div><br /></div><div>&nbsp; &nbsp;skew-symmetric: [$]\alpha(y, x) = - \alpha(x, y)[/$]</div><div><br /></div><div>&nbsp; &nbsp;there are also non-symmetric and non-skew-symmetric bilinear functions</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;bilinear form is symmetric [$]\iff[/$] [$]A^\top = A[/$]</div><div><br /></div><div>&nbsp; &nbsp;bilinear form is skew-symmetric [$]\iff[/$] [$]A^\top = - A[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;this property is independent of basis</div>
algebra bilinear_form


definition of characteristic of a ring
<div>&nbsp; if exists, the characteristic [$]\operatorname{char}(R)[/$] is the smallest [$]n[/$]</div><div>&nbsp;such that [$]\forall r \ : \ nr =0[/$]&nbsp;</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp;&nbsp;</div><div>&nbsp; if doesn't exist, then [$]\operatorname{char}(R) = 0[/$]</div><div><br /></div><div><br /></div><div>&nbsp; when [$]\operatorname{char}(R) = 1[/$], the ring is trivial set: {0, 1}</div><div><br /></div>
algebra definition

example of getting the matrix of bilinear form<div><br /></div><div><div>&nbsp; &nbsp; [$]f (x, y) = x_1 y_2 + x_1 y_3 - 2 x_3 y_1[/$]&nbsp;</div></div><div><br /></div>
<div>[$]f : F^3 \mapsto F[/$]</div><div>&nbsp; &nbsp; [$]f (x, y) = x_1 y_2 + x_1 y_3 - 2 x_3 y_1[/$]&nbsp;</div><div><br /></div><div>&nbsp; &nbsp; [$]a_{11} = f ( &lt; 1, 0, 0 &gt; , &lt; 1, 0, 0 &gt; ) = 1 \cdot 0 + 1 \cdot 0 - 2 \cdot 0 \cdot 1 = 0[/$]&nbsp;</div><div>&nbsp; &nbsp; [$]a_{12} = f ( &lt; 1, 0, 0 &gt; , &lt; 0, 1, 0 &gt; ) = 1 \cdot 1 + 1 \cdot 0 - 2 \cdot 0 \cdot 0 = 1[/$]&nbsp;</div><div>&nbsp; &nbsp; [$]a_{12} = f ( &lt; 1, 0, 0 &gt; , &lt; 0, 0, 1 &gt; ) = 1 \cdot 0 + 1 \cdot 1 - 2 \cdot 0 \cdot 0 = 1[/$]&nbsp;</div><div>&nbsp; &nbsp; [$]\ldots[/$]</div><div>&nbsp; &nbsp; [$]a_{31} = f ( &lt; 0, 0, 1 &gt; , &lt; 1, 0, 0 &gt; ) = 0 \cdot 0 + 0 \cdot 1 - 2 \cdot 1 \cdot 1 = 2[/$]</div><div>&nbsp; &nbsp; [$]\ldots[/$]</div><div>&nbsp; &nbsp; [$]a_{33} = f ( &lt; 0, 0, 1 &gt; , &lt; 0, 0, 1 &gt; ) = 0 \cdot 0 + 0 \cdot 1 - 2 \cdot 1 \cdot 0 = 0[/$]</div><div>&nbsp; &nbsp;&nbsp;</div><div>&nbsp; &nbsp; [$$]f(x,y) \ = \ &nbsp;</div><div>&nbsp; &nbsp; \begin{pmatrix} x_1 &amp; x_2 &amp; x_3 \end{pmatrix}^\top</div><div>&nbsp; &nbsp; \</div><div>&nbsp; &nbsp; \begin{pmatrix}</div><div>&nbsp; &nbsp; 0 &amp; 1 &amp; 1 \\</div><div>&nbsp; &nbsp; 0 &amp; 0 &amp; 0 \\</div><div>&nbsp; &nbsp; -2 &amp; 0 &amp; 0</div><div>&nbsp; &nbsp; \end{pmatrix}</div><div>&nbsp; &nbsp; \ \&nbsp;</div><div>&nbsp; &nbsp; \begin{pmatrix} y_1 \\ y_2 \\ y_3 \end{pmatrix}</div><div>&nbsp; &nbsp; \ = \ x_1 y_2 + x_1 y_3 - 2 x_3 y_1</div><div>&nbsp; &nbsp; [/$$]</div>
algebra bilinear_form example

<div>[$]\alpha[/$] is a bilinear form with matrix [$]A[/$]</div><div><br /></div><div><br /></div>[$]\operatorname{dim}\ker\alpha \ = \ ?[/$]
see my notes
algebra bilinear_form kernel


vector space of all bilinear forms is direct sum of subspaces: of symmetric bilinear forms and skew-symmetric bilinear forms
<div>if [$]\operatorname{char}(F) \neq 2[/$], then vector space of all bilinear forms is direct sum of subspaces: of symmetric bilinear forms and skew-symmetric bilinear forms</div><div>&nbsp; &nbsp;</div><div><br /></div><div><br /></div><div>proof: if [$]\alpha[/$] is symmetric and skew-symmetric simultaneously,</div><div><br /></div><div>then [$]\alpha(x, y) = \alpha(y, x) = - \alpha(x, y) \ \Rightarrow \ 2\alpha(x, y) = 0 \ \Rightarrow \ \alpha(x, y) = 0[/$]</div><div>&nbsp; &nbsp;</div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;i.e. every bilinear form can be represented as a sum of symmetric and skew-symmetric bilinear forms:</div><div><br /></div><div>&nbsp; &nbsp;[$]\alpha(x,y) \ &nbsp;= \ &nbsp;\frac{1}{2}\left\{ \alpha(x,y) + \alpha(y,x) \right\} \ &nbsp;+ \ &nbsp;\frac{1}{2}\left\{ \alpha(x,y) - \alpha(y,x) \right\}[/$]</div><div><br /></div><div>&nbsp; &nbsp;or in for their matrices: [$]A \ = \ &nbsp;\frac{1}{2}(A + A^\top) \ + \ &nbsp;\frac{1}{2}(A - A^\top)[/$] &nbsp;&nbsp;</div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><div>&nbsp; &nbsp;but if [$]\operatorname{char}(F) = 2[/$] the theorem does not work:</div><div><br /></div><div>&nbsp; &nbsp;[$]F = \{0, 1\}[/$], &nbsp;then a skew-symmetric form is the same as a symmetric form: [$]\alpha(-1, x) = - \alpha(1, x) = \alpha(1, x)[/$]&nbsp;</div><div><br /></div><div>&nbsp; &nbsp;and, for example, [$]\begin{pmatrix}0 &amp; 1 \\ 0 &amp; 1\end{pmatrix}[/$] can't be represented as a sum of two symmetric matrices</div></div><div><br /></div>
algebra bilinear_form

examples of symmetric and skew-symmetric matrices
<div><br /></div><div>&nbsp; &nbsp;symmetric matrix:</div><div>&nbsp; &nbsp;[$$]</div><div>&nbsp; &nbsp;\begin{pmatrix}</div><div>&nbsp; &nbsp;i &amp; 2 &amp; 3 \\</div><div>&nbsp; &nbsp;2 &amp; j &amp; 4 \\</div><div>&nbsp; &nbsp;3 &amp; 4 &amp; k</div><div>&nbsp; &nbsp;\end{pmatrix}</div><div>&nbsp; &nbsp;[/$$]</div><div>&nbsp; &nbsp;</div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;skew-symmetric matrix always have zeros on its diagonal:</div><div>&nbsp; &nbsp;[$$]</div><div>&nbsp; &nbsp;\begin{pmatrix}</div><div>&nbsp; &nbsp;0 &amp; 2 &amp; 3 \\</div><div>&nbsp; &nbsp;-2 &amp; 0 &amp; 4 \\</div><div>&nbsp; &nbsp;-3 &amp; -4 &amp; 0</div><div>&nbsp; &nbsp;\end{pmatrix}</div><div>&nbsp; &nbsp;[/$$]</div>
algebra bilinear_form matrix

definition of quadratic form
<div>[$]q(x) = \sum a_{ij} \, x_i x_j \ : \ V \mapsto F[/$]</div><div><br /></div><div>&nbsp; [$]A = (a_{ij})[/$] is the symmetric matrix of the quadratic form</div><div><br /></div>
algebra definition quadratic_form

examples of quadratic forms and their matrices
<div>[$$]x^2 - 4xy + y^2 + 5xz + 2yz + z^2 \ = \ &nbsp;x^2 - 2xy -2yx + y^2 + \frac{5}{2}xz + \frac{5}{2}zx + yz + zy + z^2 \ = \ &nbsp;\left(\begin{array}{ccc} x &amp; y &amp; z\end{array}\right) \left(\begin{array}{ccc}1 &amp; -2 &amp; \frac{5}{2} \\ -2 &amp; 1 &amp; 1 \\ \frac{5}{2} &amp; 1 &amp; 1\end{array}\right)\left(\begin{array}{ccc} x \\ y \\ z\end{array}\right)[/$$]</div><div>&nbsp;&nbsp;</div><div><br /></div><div><br /></div><div>[$]ax^2+bxy+cy^2 = \left(\begin{array}{ccc} x &amp; y \end{array}\right) \left(\begin{array}{ccc} a &amp; \frac{b}{2} \\ \frac{b}{2} &amp; c\end{array}\right)\left(\begin{array}{ccc} x \\ y \end{array}\right)[/$]</div><div>&nbsp;&nbsp;</div>
algebra example quadratic_form

relation of quadratic forms and bilinear forms
<div>any symmetric bilinear form b defines a quadratic form: [$]q(x) = \alpha(x,x)[/$]</div><div>&nbsp;&nbsp;</div><div><br /></div><div><br /></div><div>&nbsp;&nbsp;</div><div>polarization of a quadratic form (is a bilinear function): [$]\alpha(x,y)=\frac{1}{2}\left\{q(x+y)-q(x)-q(y)\right\} = x^\mathrm{T}Ay = y^\mathrm{T}Ax[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp;&nbsp;</div><div>&nbsp; matrix of a polar bilinear form is equal to matrix of quadratic form&nbsp;&nbsp;</div>
algebra example quadratic_form

definition of&nbsp;orthogonal complement of a subspace [$]W[/$] of a vector space [$]V[/$] equipped with a bilinear form
<div>set [$]W^\bot[/$] of all vectors in [$]V[/$] that are orthogonal to every vector in [$]W[/$]</div><div><br /></div><div>&nbsp; &nbsp;[$]W^\bot = \left\{x\in V \ &nbsp;: \ &nbsp;\forall y\in W \ \alpha(x, y) = 0 \right\}[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;[$]V^\bot = \operatorname{Ker}\alpha[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;if [$]\alpha(x, y) \not\equiv 0[/$], then [$]\dim W + \dim {W^\bot} = \dim V[/$]&nbsp;</div><div><br /></div><div>&nbsp; &nbsp;and [$](W^\bot)^\bot = W[/$]</div><div><br /></div>
algebra bilinear_form definition

definition of orthogonal vectors in respect to a bilinear form
<div>&nbsp; &nbsp;[$]x[/$] and [$]y[/$] are /orthogonal/ if [$]\alpha(x, y) = 0[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><div>&nbsp; &nbsp;[$]\operatorname{char} F \neq 2[/$]</div></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;when bilinear form is skew-symmetric, every vector is orthogonal to itself</div><div><br /></div>
algebra bilinear_form definition

Gram–Schmidt process --- orthonormalising a set of vectors
"<div>&nbsp;[$$]\mathrm{proj}_{\mathbf{b}}\,\mathbf{a} = {\langle \mathbf{b}, \mathbf{a}\rangle\over\langle \mathbf{b}, \mathbf{b}\rangle}\mathbf{b}[/$$]</div><div>&nbsp; &nbsp;&nbsp;</div><div>&nbsp; &nbsp;&nbsp;</div><div>[latex]<div>&nbsp; &nbsp; \begin{align*}</div><div>&nbsp; &nbsp; \mathbf{b}_1 &amp; = \mathbf{a}_1, &amp; \mathbf{e}_1 &amp; = {\mathbf{b}_1 \over \|\mathbf{b}_1\|} \\</div><div>&nbsp; &nbsp; \mathbf{b}_2 &amp; = \mathbf{a}_2-\mathrm{proj}_{\mathbf{b}_1}\,\mathbf{a}_2,</div><div>&nbsp; &nbsp; &amp; \mathbf{e}_2 &amp; = {\mathbf{b}_2 \over \|\mathbf{b}_2\|} \\</div><div>&nbsp; &nbsp; \mathbf{b}_3 &amp; = \mathbf{a}_3- \left( \mathrm{proj}_{\mathbf{b}_1}\,\mathbf{a}_3+\mathrm{proj}_{\mathbf{b}_2}\,\mathbf{a}_3 \right), &amp; \mathbf{e}_3 &amp; = {\mathbf{b}_3 \over \|\mathbf{b}_3\|} \\</div><div>&nbsp; &nbsp; \mathbf{b}_4 &amp; = \mathbf{a}_4- \left( \mathrm{proj}_{\mathbf{b}_1}\,\mathbf{a}_4+\mathrm{proj}_{\mathbf{b}_2}\,\mathbf{a}_4+\mathrm{proj}_{\mathbf{b}_3}\,\mathbf{a}_4 \right), &amp; \mathbf{e}_4 &amp; = {\mathbf{b}_4 \over \|\mathbf{b}_4\|} \\</div><div>&nbsp; &nbsp; &amp; {}\ \ &nbsp;\vdots &amp; &amp; {}\ \ &nbsp;\vdots \\</div><div>&nbsp; &nbsp; \mathbf{b}_k &amp; = \mathbf{a}_k-\sum_{j=1}^{k-1}\mathrm{proj}_{\mathbf{b}_j}\,\mathbf{a}_k, &amp; \mathbf{e}_k &amp; = {\mathbf{b}_k\over \|\mathbf{b}_k \|}.</div><div>&nbsp; &nbsp; \end{align*}</div>[/latex]</div><div><br /></div><div><img src=""20130503-1233-379yXc.screenshot.png"" /></div><div><br /></div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;[$]\mathbf{b}_1[/$] and [$]\mathbf{b}_2[/$] are orthogonal:</div><div>&nbsp; &nbsp;[$$]\langle\mathbf{b}_1, \mathbf{b}_2\rangle = \langle\mathbf{b}_1, \mathbf{a}_2-\mathrm{proj}_{\mathbf{b}_1}\,\mathbf{a}_2\rangle = \langle\mathbf{b}_1, \mathbf{a}_2\rangle - \langle\mathbf{b}_1, \mathrm{proj}_{\mathbf{b}_1}\,\mathbf{a}_2\rangle = \langle\mathbf{b}_1, \mathbf{a}_2\rangle - \langle\mathbf{b}_1, {\langle \mathbf{b}_1, \mathbf{a}_2\rangle\over\langle \mathbf{b}_1, \mathbf{b}_1\rangle} \mathbf{b}_1 \rangle = \langle\mathbf{b}_1, \mathbf{a}_2\rangle - {\langle \mathbf{b}_1, \mathbf{a}_2\rangle\over\langle \mathbf{b}_1, \mathbf{b}_1\rangle} \langle\mathbf{b}_1, \mathbf{b}_1 \rangle = 0[/$$]&nbsp;</div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;[$]\mathbf{b}_2[/$] and [$]\mathbf{b}_3[/$] are orthogonal similarly:</div><div>&nbsp; &nbsp;[$$]\langle\mathbf{b}_2, \mathbf{b}_3\rangle = \langle\mathbf{b}_2, \mathbf{a}_3- \left( \mathrm{proj}_{\mathbf{b}_1}\,\mathbf{a}_3+\mathrm{proj}_{\mathbf{b}_2}\,\mathbf{a}_3 \right)\rangle = \langle\mathbf{b}_2, \mathbf{a}_3\rangle - 0 - \langle\mathbf{b}_2, \mathrm{proj}_{\mathbf{b}_2}\,\mathbf{a}_3\rangle[/$$]</div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;etc</div><div>&nbsp; &nbsp;</div>"
algebra bilinear_form

canonical, or normal form of quadratic function
<div>&nbsp; &nbsp;If [$]F = \mathbb C[/$],&nbsp;coefficients&nbsp;[$]\alpha_i = 0, 1[/$],&nbsp;</div><div><br /></div><div><br /></div><div>i.e. canonical quadratic function look like</div><div><br /></div><div>&nbsp;[$]q(x) = x_1^2 + \ldots + x_r^2[/$]&nbsp;after a suitable permutation of basis vectors,&nbsp;</div><div><br /></div><div><br /></div><div>[$]r = \operatorname{rank} q[/$].</div><div>&nbsp; &nbsp;</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;If [$]F = \mathbb R[/$], coefficients [$]\alpha_i = -1, 0, 1[/$],&nbsp;</div><div><br /></div><div>i.e. canonical quadratic function look like</div><div><br /></div><div>&nbsp;[$]q(x) = x_1^2 + \ldots + x_k^2 - x_{k+1}^2 - \ldots - x_{k+l}^2[/$] after a suitable permutation of basis vectors.</div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;[$]k+l = \operatorname{rank} q[/$]</div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;a pair [$](k,l)[/$] is called signature of [$]q[/$]</div>
algebra quadratic_form

law of inertia for quadratic forms
"<div>&nbsp; &nbsp;[$]k[/$] and [$]l[/$] do not depend on a particular choice of diagonalizing basis</div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;// it's about invariant signature, the word ""inertia"" was used because no better word was found</div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;[$]k[/$] is max dimention of a subspace on which [$]q(x)[/$] is positive definite</div><div><br /></div><div>&nbsp; &nbsp;(same for [$]l[/$])</div><div><br /></div>"
algebra quadratic_form

definition of&nbsp;positive definite and negative definite quadratic forms
<div>&nbsp; &nbsp;[$]q(x) &gt; 0[/$] for [$]x \neq 0[/$] is positive definite</div><div><br /></div><div>&nbsp; &nbsp;[$]q(x) &lt; 0[/$] for [$]x \neq 0[/$] is negative definite</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;bilinear form [$]\alpha(x, y)[/$] is positive definite if associated quadratic form [$]q(x)[/$] is positive definite (same for negative)</div><div><br /></div><div>&nbsp; &nbsp;dot product [$](x, y)[/$] of vectors is positive definite</div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;normal form of positive definite quadratic function is [$]q(x) = x_1^2 + \ldots + x_k^2[/$]</div>
algebra quadratic_form

Sylvester's criterion --- is a quadratic form positive definite
<div>&nbsp;a matrix [$]A[/$] is positive definite&nbsp;</div><div>[$]\iff[/$]&nbsp;</div><div>all the following matrices have a positive determinant:</div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;the upper left 1-by-1 corner</div><div>&nbsp; &nbsp;the upper left 2-by-2 corner</div><div>&nbsp; &nbsp;...</div><div>&nbsp; &nbsp;the upper left n-by-n corner -- [$]A[/$] itself</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;[$$]A = \begin{pmatrix} a_{11} &amp; a_{12} &amp; \ldots &amp; a_{1n} \\ a_{21} &amp; a_{22} &amp; \ldots &amp; a_{2n} \\ \ldots &amp; \ldots &amp; \ldots &amp; \ldots \\ a_{n1} &amp; a_{n2} &amp; \ldots &amp; a_{nn} \end{pmatrix}[/$$]</div><div><br /></div><div>&nbsp; &nbsp;[$$]\Delta_1=a_{11}[/$$]</div><div><br /></div><div>&nbsp; &nbsp;[$$]\Delta_2=\begin{vmatrix}a_{11} &amp; a_{12} \\ a_{21} &amp; a_{22}\end{vmatrix}[/$$]</div><div><br /></div><div>&nbsp; &nbsp;[$$]\Delta_3=\begin{vmatrix}a_{11} &amp; a_{12} &amp; a_{13} \\ a_{21} &amp; a_{22} &amp; a_{23} \\ a_{31} &amp; a_{32} &amp; a_{33}\end{vmatrix}[/$$]</div><div><br /></div><div>&nbsp; &nbsp;[$$]\Delta_i=\begin{vmatrix} a_{11} &amp; a_{12} &amp; \ldots &amp; a_{1i} \\ a_{21} &amp; a_{22} &amp; \ldots &amp; a_{2i} \\ \ldots &amp; \ldots &amp; \ldots &amp; \ldots \\ a_{i1} &amp; a_{i2} &amp; \ldots &amp; a_{ii}\end{vmatrix}[/$$]</div><div><br /></div><div>&nbsp; &nbsp;[$$]\Delta_n = |A|[/$$]</div><div>&nbsp; &nbsp;</div><div><br /></div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;in another words, all leading principal minors are positive</div><div>&nbsp; &nbsp;</div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;if every [$]\Delta_k[/$] is non-zero then the negative index of inertia is equal to the number of sign changes in the sequence [$]\Delta_0=1, \Delta_1, \ldots, \Delta_n=\det A[/$]</div><div><br /></div>
algebra quadratic_form

definition of eigenvector and eigenvalue
see my notes
algebra eigenvector

definition of eigenspace
<div>/eigenspace/ associated with an eigenvalue&nbsp;</div><div><br /></div><div>[$]V^{\lambda} = \left\{ \ x \ &nbsp;: \ &nbsp;A x = \lambda x \ &nbsp;\right\}[/$]&nbsp;</div><div><br /></div><div>consists of [$]\boldsymbol 0[/$] and all eigenvectors associated with the eigenvalue</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;eigenspace is a subspace since nonempty and [$]Ax = \lambda x, \ &nbsp;Ay = \lambda y \ &nbsp;\Rightarrow \ &nbsp;A(\alpha x + \beta y) = \lambda (\alpha x + \beta y)[/$]</div><div>&nbsp; &nbsp;</div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;eigenspaces are linearly independent</div><div>&nbsp; &nbsp;i.e. eigenvectors corresponding to different eigenvalues are linearly independent</div><div>&nbsp; &nbsp;</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;[$]\dim V^{\lambda}[/$] is /geometric multiplicity/ of an eigenvalue [$]\lambda[/$]</div>
algebra eigenvector

characteristic polynomial of a linear operator
<div>&nbsp; &nbsp;The eigenvalues of a matrix A are precisely the solutions [$]\lambda[/$] to the equation</div><div><br /></div><div>&nbsp; &nbsp;[$]\det(A - \lambda I) = 0[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;proof:</div><div><br /></div><div>&nbsp; &nbsp;[$]Ax = \lambda x \ \Leftrightarrow \ Ax - \lambda I x = 0 &nbsp;\ \Leftrightarrow \ (A - \lambda I) x = 0[/$]</div><div><br /></div><div>&nbsp; &nbsp;If there exists an inverse [$](A - \lambda I)^{-1}[/$] then both sides can be left-multiplied by it to obtain [$]x=0[/$].&nbsp;</div><div><br /></div><div>&nbsp; &nbsp;Therefore, if [$]\lambda[/$] is such that [$](A - \lambda I)[/$] is invertible, [$]\lambda[/$] cannot be an eigenvalue.</div><div><br /></div><div>&nbsp; &nbsp;If it is not invertible, [$]\lambda[/$] is an eigenvalue.</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><div>&nbsp; &nbsp;[$$]\det(A-\lambda I) = \begin{vmatrix} a_{11} - \lambda &amp; a_{12} &amp; \ldots &amp; a_{1n} \\ a_{21} &amp; a_{22} - \lambda &amp; \ldots &amp; a_{2n} \\ \ldots &amp; \ldots &amp; \ldots &amp; \ldots \\ a_{n1} &amp; a_{n2} &amp; \ldots &amp; a_{nn} - \lambda \end{vmatrix}[/$$]</div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;/characteristic polynomial/ [$]\chi_{\mathcal A}(t) = \det(tI - A)[/$] &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ( [$]= (-1)^n \, \det(A-tI)[/$] )</div><div><br /></div><div>&nbsp; &nbsp;The solutions of the /characteristic equation/ [$]\chi_A(t) = 0[/$] are precisely the eigenvalues.</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;Two similar matrices have the same characteristic polynomial: [$]\chi_{C^{-1}AC} (t)=\chi_{A}(t)[/$]</div><div><br /></div><div>&nbsp; &nbsp;/similar/: [$]C[/$] is invertible change of basis. [$]A' = C^{-1}AC[/$]. Then [$]\det(tI - A') = \det(tC^{-1}IC - C^{-1}AC) = \det\left( C^{-1} (tI -A) C \right) = \det C^{-1} \det(tI - A) \det C = \det(tI - A)[/$]</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;We can assume [$]\chi_{\mathcal A}(t) = \chi_A(t)[/$]</div><div><br /></div><div>&nbsp; &nbsp;characteristic polynominal does not depend on the choice of a basis</div></div><div><br /></div>
algebra eigenvector

<div>&nbsp; &nbsp; [$]f(x) = (x - \lambda_1)^{d_1} \ldots (x - \lambda_k)^{d_k}[/$]&nbsp;</div><div><br /></div><div>&nbsp; &nbsp; [$]\operatorname{tr}(A) \ = \ ?[/$]</div><div><br /></div>
<div><div>&nbsp; &nbsp; [$]\operatorname{tr}(A) = d_1 \lambda_1 + \cdots + d_k \lambda_k[/$]</div></div><div><br /></div>
algebra eigenvector

A has eigenvalues [$]\lambda_1, \ldots, \lambda_n[/$]<div><br /></div><div>[$]\det A = ?[/$]</div>
<div>[$]\det A = \prod \lambda_i[/$]</div><div><br /></div>
algebra eigenvector

relation of invertible matrices and eigenvalues
<div>&nbsp; &nbsp;matrix is invertible [$]\iff[/$] no zero eigenvalue</div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;if [$]A[/$] is invertible, then eigenvalues of [$]A^{-1}[/$] are [$]\frac{1}{\lambda_1}, \ldots, \frac{1}{\lambda_n}[/$]</div><div>&nbsp; &nbsp;</div>
algebra eigenvector

examples of eigenvalues and eigenvectors
<div>&nbsp; &nbsp;[$$]</div><div>&nbsp; &nbsp;A =</div><div>&nbsp; &nbsp;\begin{pmatrix}</div><div>&nbsp; &nbsp;2 &amp; 0 &amp; 0 \\</div><div>&nbsp; &nbsp;0 &amp; 3 &amp; 4 \\</div><div>&nbsp; &nbsp;0 &amp; 4 &amp; 9</div><div>&nbsp; &nbsp;\end{pmatrix}</div><div>&nbsp; &nbsp;[/$$]</div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;characteristic polynomial:</div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;[$$]</div><div>&nbsp; &nbsp;\det (A-\lambda I) \ = \ &nbsp;</div><div>&nbsp; &nbsp;\det \left(\begin{bmatrix}</div><div>&nbsp; &nbsp;2 &amp; 0 &amp; 0 \\</div><div>&nbsp; &nbsp;0 &amp; 3 &amp; 4 \\</div><div>&nbsp; &nbsp;0 &amp; 4 &amp; 9</div><div>&nbsp; &nbsp;\end{bmatrix} - \lambda</div><div>&nbsp; &nbsp;\begin{bmatrix}</div><div>&nbsp; &nbsp;1 &amp; 0 &amp; 0 \\</div><div>&nbsp; &nbsp;0 &amp; 1 &amp; 0 \\</div><div>&nbsp; &nbsp;0 &amp; 0 &amp; 1</div><div>&nbsp; &nbsp;\end{bmatrix}\right) \;=\;</div><div>&nbsp; &nbsp;\det \begin{bmatrix}</div><div>&nbsp; &nbsp;2 - \lambda &amp; 0 &amp; 0 \\</div><div>&nbsp; &nbsp;0 &amp; 3 - \lambda &amp; 4 \\</div><div>&nbsp; &nbsp;0 &amp; 4 &amp; 9 - \lambda</div><div>&nbsp; &nbsp;\end{bmatrix} = &nbsp;(2 - \lambda) \bigl[ (3 - \lambda) (9 - \lambda) - 16 \bigr] = \lambda^3 -14\lambda^2 + 35\lambda - 22</div><div>&nbsp; &nbsp;[/$$]</div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;eigenvalues are 1, 2, 11</div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;when we have eigenvalues, we can get corresponding eigenvectors from a system of linear equations:</div><div>&nbsp; &nbsp;[$]Ax = \lambda x[/$]</div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;</div><div><br /></div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;another example</div><div>&nbsp; &nbsp;[$$]A = \begin{bmatrix} 4 &amp; 1\\6 &amp; 3 \end{bmatrix}[/$$]</div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;[$]\lambda_1 = 1, \ \lambda_2 = 6[/$]</div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;[$$]\begin{bmatrix} 4 &amp; 1\\6 &amp; 3 \end{bmatrix}\begin{bmatrix}x\\y\end{bmatrix} = 6 \cdot \begin{bmatrix}x\\y\end{bmatrix}[/$$]</div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;[$$]</div><div>&nbsp; &nbsp;\left\{\begin{matrix} 4x + {\ }y &amp;{}= 6x\\6x + 3y &amp;{}=6 y\end{matrix}\right.</div><div>&nbsp; &nbsp;\quad\quad\quad</div><div>&nbsp; &nbsp;[/$$]</div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;[$]y = 2x[/$]</div><div>&nbsp; &nbsp;</div><div>&nbsp; &nbsp;[$]\Rightarrow[/$] for an eigenvalue 6 the eigenvectors are [$](a, 2a)[/$] for nonzero [$]a[/$]</div><div><br /></div>
algebra eigenvector example

definition and properties of diagonizable linear operator
see my notes
algebra eigenvector

proove that row rank is equal to column rank
***
algebra matrix rank

proove that&nbsp;<div><br /></div><div><div>&nbsp; &nbsp; [$]\operatorname{rank}A = r[/$] &nbsp; [$]\iff[/$] &nbsp;&nbsp;</div><div><br /></div><div><br /></div><div>&nbsp; &nbsp; [$]\exists[/$] invertible matrices [$]X_{m \times m}[/$] and [$]Y_{n \times n}[/$] such that&nbsp;</div><div>&nbsp; &nbsp; [$$]XAY = &nbsp;\begin{bmatrix} &nbsp; &nbsp;I_r &amp; 0 \\ &nbsp; &nbsp;0 &amp; 0 \\ &nbsp;\end{bmatrix}[/$$]</div></div><div><br /></div>
***
algebra matrix rank

illustration of matrix multiplication
"<div><img src=""20150227-1802-32099XmF.screenshot.png"" /></div>"
algebra matrix

rank of real matrix
for real matrices: [$]\operatorname{rank}(A^T A) = \operatorname{rank}(A A^T) = \operatorname{rank}(A) = \operatorname{rank}(A^T)[/$]<div><br /></div><div>see my notes</div>
algebra matrix rank

rank of complex matrix
<div>for real matrices: [$]\operatorname{rank}(R^T R) = \operatorname{rank}(R R^T) = \operatorname{rank}(R) = \operatorname{rank}(R^T)[/$]</div><div>&nbsp; &nbsp; for complex matrices: [$]\operatorname{rank}(C) = \operatorname{rank}(\overline{C}) = \operatorname{rank}(C^T) = \operatorname{rank}(C^*) = \operatorname{rank}(C^*C)[/$], where [$]C^* = \overline{C^T} = (\overline{C})^T[/$]</div><div>&nbsp; &nbsp;&nbsp;</div>
algebra matrix rank

property of rank<div><br /></div><div>[$]\operatorname{rank}(AB) + \operatorname{rank}(BC)[/$]</div>
[$]\operatorname{rank}(AB) + \operatorname{rank}(BC) \le \operatorname{rank}(B) + \operatorname{rank}(ABC)[/$]
algebra matrix rank

gramian matrix
<div>gramian matrix for a set of vectors is [$]G_{ij}=\langle v_j, v_i \rangle[/$]</div><div><br /></div><div><br /></div><div>[$$]\det</div><div>&nbsp; &nbsp; \begin{pmatrix}&nbsp;</div><div>&nbsp; &nbsp; \langle v_1,\;v_1\rangle &amp; \langle v_1,\;v_2\rangle &amp; \ldots &amp; \langle v_1,\;v_n\rangle \\&nbsp;</div><div>&nbsp; &nbsp; \langle v_2,\;v_1\rangle &amp; \langle v_2,\;v_2\rangle &amp; \ldots &amp; \langle v_2,\;v_n\rangle \\&nbsp;</div><div>&nbsp; &nbsp; \ldots &amp; \ldots &amp; \ldots &amp; \ldots \\&nbsp;</div><div>&nbsp; &nbsp; \langle v_n,\;v_1\rangle &amp; \langle v_n,\;v_2\rangle &amp; \ldots &amp; \langle v_n,\;v_n\rangle&nbsp;</div><div>&nbsp; &nbsp; \end{pmatrix} =</div><div>&nbsp; &nbsp; \det \left(</div><div>&nbsp; &nbsp; \begin{pmatrix}</div><div>&nbsp; &nbsp; v_{11} &amp; \ldots &amp; v_{1n} \\</div><div>&nbsp; &nbsp; \ldots &amp; \ldots &amp; \ldots \\</div><div>&nbsp; &nbsp; v_{n1} &amp; \ldots &amp; v_{nn}</div><div>&nbsp; &nbsp; \end{pmatrix}</div><div>&nbsp; &nbsp; \begin{pmatrix}</div><div>&nbsp; &nbsp; v_{11} &amp; \ldots &amp; v_{1n} \\</div><div>&nbsp; &nbsp; \ldots &amp; \ldots &amp; \ldots \\</div><div>&nbsp; &nbsp; v_{n1} &amp; \ldots &amp; v_{nn}</div><div>&nbsp; &nbsp; \end{pmatrix}^\top</div><div>&nbsp; &nbsp; \right) = \det (VV^\top) = \det V \det V^\top = (\det V)^2 \geqslant 0</div><div>&nbsp; &nbsp; [/$$]</div>
algebra matrix

<div><div>solution set to any homogeneous system of linear equations with n variables is a subspace of [$]F^n[/$].</div></div>
<div><div>for example, the set of all vectors [$](x, y, z)[/$] satisfying the equations [$]x + 3y + 2z = 0[/$] and [$]2x - 4y + 5z = 0[/$] is a one-dimensional subspace of [$]\mathbb R^3[/$].</div></div><div><br /></div>
algebra homogeneous_system matrix rank systems_of_linear_equations vector_space

<div>[$]U[/$] and&nbsp;[$]W[/$] are vector subspaces</div><div><br /></div><div><br /></div><div>[$]\operatorname{dim} (U+W) = ?[/$]</div><div><br /></div>
<div>[$]\operatorname{dim} (U+W) = \operatorname{dim} U + \operatorname{dim} W - \operatorname{dim} (U \cap W)[/$]</div><div><br /></div>


is it always [$]\operatorname{rank}(A^T A) = \operatorname{rank}(AA^T) = \operatorname{rank}(A)[/$]?
see my notes
algebra matrix rank

knowing two solutions of [$]Ax=b[/$], how to get a solution of homogeneous system&nbsp;[$]Ax=0[/$]
<div>&nbsp; &nbsp;&nbsp;</div><div>&nbsp; &nbsp; if [$]x_1[/$], [$]x_2[/$] are solutions for [$]Ax=b[/$]</div><div>&nbsp; &nbsp; then [$]x_1 - x_2[/$] is solution for the homogenous system [$]Ax=0[/$]</div><div>&nbsp; &nbsp; [$]A (x_1 - x_2) = b - b = 0[/$]</div>
algebra homogeneous_system

prove that a vector in a basis can be interchanged with some another vector from a second basis
see my notes
algebra basis vector_space

prove that bases have equal number of vectors
see my notes
algebra basis vector_space

Does there exist an isomorphism between [$]\mathbb R^2[/$] and [$]\mathbb R^3[/$]
see my notes
algebra basis vector_space

illustration of eigenvectors
see my notes
algebra eigenvector

definition of vector space
<br /><i>vector space V over field F is an abelian group (V, +) with multiplication by elements of F</i><br /><br />----------------------------------------------------------------------------------------------------------------------<br /><br /><br /><br /><br /><br /><br /><br /><br />vector space V over field F:<br /><br /><br /><br /><br />abelian group (V, +)<br /><br /><br /><br /><br />multiplication by elements of F<br /><br />[$]\lambda (a+b) = \lambda a + \lambda b[/$]<br /><br />[$](\lambda + \mu) a = \lambda a + \mu a[/$]<br /><br />[$]\lambda (\mu a) = (\lambda \mu) a[/$]<br /><br />[$]1 \cdot a = a[/$]
algebra definition vector_space
