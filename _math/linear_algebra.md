---
title:  "Linear algebra"
layout: default

---

# TODOs

reverse of 2x2 matrix `d & -b \\ -c & a`



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
