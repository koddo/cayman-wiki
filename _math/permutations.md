---
title:  "Permutations"
layout: default

---

$$
\begin{align*}
(\tau \sigma)(i) = \tau (\sigma (i)) &= \begin{pmatrix} 1 & 2 & 3 & 4 & 5 & 6 \\ 3 & 5 & 1 & 6 & 2 & 4 \end{pmatrix} \cdot \begin{pmatrix} 1 & 2 & 3 & 4 & 5 & 6 \\ 6 & 3 & 4 & 2 & 1 & 5 \end{pmatrix} = \\ 
&= \begin{pmatrix} 1 & 2 & 3 & 4 & 5 & 6 \\ 4 & 1 & 6 & 5 & 3 & 2 \end{pmatrix} \ \ \ \ \ \ \ \ \ (\text{right to left: } 1 \to 6 \to 4)
\end{align*}
$$
   
cycle --- $\begin{pmatrix}1 & 2 & 5 \end{pmatrix}$
transposition --- cycle of length two: $\begin{pmatrix}3 & 4 \end{pmatrix}$


write the permutation as a product of disjoint cycles
$$
\begin{align*}
\begin{pmatrix} 1 & 2 & 3 & 4 & 5 & 6 & 7 \\ 5 & 4 & 1 & 7 & 3 & 6 & 2 \end{pmatrix} &= \begin{pmatrix} 1 & 5 & 3 \end{pmatrix} \begin{pmatrix} 2 & 4 & 7 \end{pmatrix} = \\
&= \begin{pmatrix} 1 & 5 & 3 \end{pmatrix} \begin{pmatrix} 2 & 4 & 7 \end{pmatrix} \begin{pmatrix} 6 \end{pmatrix} = \\
&= \begin{pmatrix} 2 & 4 & 7 \end{pmatrix} \begin{pmatrix} 1 & 5 & 3 \end{pmatrix} = \\
&= \begin{pmatrix} 2 & 4 & 7 \end{pmatrix} \begin{pmatrix} 1 & 5 & 3 \end{pmatrix} \begin{pmatrix} 6 \end{pmatrix}
\end{align*}
$$


multiply permutations:
$$\left[\begin{pmatrix} 1 & 3 & 5 \end{pmatrix} \begin{pmatrix} 2 & 4 & 6 & 7 \end{pmatrix}\right] \  \cdot \ \left[\begin{pmatrix} 1 & 4 & 7 \end{pmatrix} \begin{pmatrix} 2 & 3 & 5 & 6 \end{pmatrix}\right] = \begin{pmatrix} 1 & 6 & 4 & 2 & 5 & 7 & 3 \end{pmatrix}$$

$$
\begin{align*}
1 \to 4 \to 6&: \ \ \ \begin{pmatrix} 1 & 6 & \ldots \end{pmatrix} \\
6 \to 2 \to 4&: \ \ \ \begin{pmatrix} 1 & 6 & 4 & \ldots \end{pmatrix} \\
4 \to 7 \to 2&: \ \ \ \begin{pmatrix} 1 & 6 & 4 & 2 & \ldots \end{pmatrix}
\end{align*}
$$

to inverse a permutation just interchange the two lines:
$$
\begin{pmatrix} 1 & 2 & 3 & 4 & 5 \\ \boldsymbol 2 & \boldsymbol 5 & \boldsymbol 4 & \boldsymbol 3 & \boldsymbol 1 \end{pmatrix}^{-1}
    =\begin{pmatrix} \boldsymbol 2 & \boldsymbol 5 & \boldsymbol 4 & \boldsymbol 3 & \boldsymbol 1 \\ 1 & 2 & 3 & 4 & 5 \end{pmatrix}
    =\begin{pmatrix} 1 & 2 & 3 & 4 & 5 \\ 5 & 1 & 4 & 3 & 2\end{pmatrix}
$$


inverted cycle: $\begin{pmatrix} i_1 & \ldots & i_n \end{pmatrix}^{-1} = \begin{pmatrix} i_n & \ldots & i_1 \end{pmatrix}$



there are two equivalent definitions of /parity/

the parity of a permutation is the parity of number of inversions
inversion is a pair of elements $(x, \, y)$ such that $x < y$ and $\sigma(x) > \sigma(y)$
  

the parity of a permutation is the parity of number of transpositions in the decomposition
although such a decomposition is not unique, the parity of the number of transpositions in all decompositions is invariant, implying that the sign of a permutation is well-defined

Theorem: two definitions are equivalent

Proof: $(-1)^n$ where $n$ is number of inversions can be written as

$$\operatorname{sgn}(\sigma)=\frac{P(x_{\sigma(1)},\ldots,x_{\sigma(n)})}{P(x_1,\ldots,x_n)}$$

where
$$P(x_1,\ldots,x_n)=\prod_{i<j} (x_i - x_j)\;$$

e.g. $P(x_1, x_2, x_3) = (x_1 - x_2)(x_1 - x_3)(x_2 - x_3)\;$

e.g. $\operatorname{sgn}(e) = 1$ and $\operatorname{sgn}(1\ 2) = -1$

$\operatorname{sgn}(\sigma\tau) = \operatorname{sgn}(\sigma)\cdot\operatorname{sgn}(\tau)$

because
$$
\begin{align*}
\operatorname{sgn}(\sigma\tau) &= \frac{P(x_{\sigma(\tau(1))},\ldots,x_{\sigma(\tau(n))})}{P(x_1,\ldots,x_n)} = \\
&= \frac{P(x_{\sigma(\tau(1))},\ldots, x_{\sigma(\tau(n))})}{P(x_1,\ldots,x_n)} \cdot \frac{P(x_{\sigma(1)},\ldots,x_{\sigma(n)})}{P(x_{\sigma(1)},\ldots,x_{\sigma(n)})} = \\
&= \frac{P(x_{\sigma(1)},\ldots,x_{\sigma(n)})}{P(x_1,\ldots,x_n)} \cdot \frac{P(x_{\sigma(\tau(1))},\ldots, x_{\sigma(\tau(n))})}{P(x_{\sigma(1)},\ldots,x_{\sigma(n)})} = \\
&= \operatorname{sgn}(\sigma)\cdot\operatorname{sgn}(\tau)
\end{align*}
$$

then if there are two representations $\sigma \ = \ a_1 \ldots a_n \ = \ b_1 \ldots b_k$
then $\operatorname{sgn}(\sigma) = (-1)^n = (-1)^k$
then $n-k$ is even
therefore 
either both of them are even 
or both of them are odd

End proof.

Example
is the permutation even or odd?
$$\begin{pmatrix} 1 & 2 & 3 & 4 & 5 & 6 & 7 \\ 5 & 6 & 2 & 7 & 4 & 1 & 3 \end{pmatrix}$$

let's count inversions

$\sigma(1) > \sigma(3),\,\sigma(5),\,\sigma(6),\,\sigma(7)$
$\sigma(2) > \ldots$
...

$\Updownarrow$

5 > 2,4,1,3 --- 4 inversions
6 > 2,4,1,3 --- 4 inversions
2 > 1 --- 1 inversion
7 > 4,1,3 --- 3 inversions
4 > 1,3 --- 2 inversions

4 + 4 + 1 + 3 + 2 = 14 --- the permutation is even

Another example:
the sign of $n$-cycle is $(-1)^{n-1}$ since
every $n$-cycle can be expressed as product of $n-1$ transpositions:
$\begin{pmatrix} 1 & 2 & \ldots & n \end{pmatrix} = \begin{pmatrix} 1 & n \end{pmatrix} \cdot \begin{pmatrix} 1 & (n-1) \end{pmatrix} \cdot \ldots \cdot \begin{pmatrix} 1 & 3 \end{pmatrix} \cdot \begin{pmatrix} 1 & 2 \end{pmatrix}$
and also
$\begin{pmatrix} 1 & 2 & \ldots & n \end{pmatrix} = \begin{pmatrix} 1 & 2 \end{pmatrix} \cdot \begin{pmatrix} 2 & 3 \end{pmatrix} \cdot \ldots \cdot \begin{pmatrix} {n-1} & n \end{pmatrix}$ 


in practice, in order to determine whether a given permutation is even or odd, one writes the permutation as a product of disjoint cycles
$\sigma = c_1 \cdot \ldots \cdot c_n$, where $c_1, \ldots, c_n$ are cycles
$\operatorname{sgn} \sigma = (-1)^{\operatorname{parity}(c_1) + \ldots + \operatorname{parity}(c_n)}$


transposition changes parity of a permutation

number of even permutations is the same as number of odd permutations --- multiply an even permutation by a transposition and get an odd one, this defines a bijection



the following rules follow directly from addition of numbers of transpositions:
- the composition of two even permutations is even
- the composition of two odd permutations is even
- the composition of an odd and an even permutation is odd
    
permutation is odd $\iff$ disjoint cycles factorization contains an odd number of odd cycles






Any even permutation can be written as a product of cycles of length three:

if j = k then (i j)(k l) = (i j l) is a 3-cycle
otherwise, (i j)(k l) = (i j)(j k) (j k)(k l) = (i j k)(j k l)


- Q: Properties of parity:
  - $\operatorname{sgn}(\sigma \tau) = \operatorname{sgn}(\sigma) \operatorname{sgn}(\tau)$
  - $\operatorname{sgn}(1) = 1$
  - $\operatorname{sgn}(\sigma^{-1}) = (\operatorname{sgn}(\sigma))^{-1} = \operatorname{sgn}(\sigma)$
  - $\operatorname{sgn}(i_1 \ldots i_n) = (-1)^{n-1}$
  - $\operatorname{sgn}(t) = -1$

- Q: Number of vertices minus number of cycles minus number of fixed points. Which is number of vertices minus number of components if drawn as graph.

- Q: There exists exactly one function $\operatorname{sgn}: S_n \to {\plusminus 1}$ not equivalent to one, with properties $\operatorname{sgn}(\sigma \tau) = \operatorname{sgn}(\sigma) \operatorname{sgn}(\tau)$

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- permutations">
    <p>Your browser does not support iframes.</p>
</iframe>

- Q: $\prod_{\sigma \in S_n} \operatorname{sgn}(\sigma) = ?$
- A: It equals to number of odd permutations, which is half of all permutations.


- Q: Any even permutation can be written as a product of these cycles: (1 2 3), (1 2 4), ... , (1 2 n):

- Q: Any even permutation can be written as a product of cycles of length three: (a k l)
- A: 
we've got these elementary cycles:
(1 2 3),       (1 3 2) = (1 2 3)^2 
(1 2 4),       (1 4 2) = (1 2 4)^2 
.....
(1 2 n),       (1 n 2) = (1 2 n)^2 

then (1 k l) = (1 2 l) (1 k 2) =
             = (1 2 l) (2 1 k)

put a instead of 1:
(a k l) = (a 2 l) (a k 2) =
        = (2 l a) (2 a k) =    interchange 1 and 2 in (1 k l) 
        = (2 1 a) (1 2 l) (2 1 k) (1 2 a)

- Q: <https://en.wikipedia.org/wiki/Vandermonde_matrix>

- Q: How to solve $x^2 = \sigma$?

- Q: Every $n$-cycle can be expressed as product of $n−1$ transpositions.

- Q: How to find parity of a permutation?

- Q: Solve $(1 \  2) \sigma (3 \  4) = ((1\ 2\ 3)(4\ 5))^17$.

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- permutations -- problems">
    <p>Your browser does not support iframes.</p>
</iframe>
