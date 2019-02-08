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

Also, parity is $(-1)^{\operatorname{dec}(\sigma)}$, where decrement $\operatorname{dec}(\sigma) = n - \text{number of cycles} - \text{number of fixed points} = \text{number of points} - \text{number of graph components}$

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

- Q: There exists exactly one function $\operatorname{sgn}: S_n \to {\pm 1}$ not equivalent to one, with properties $\operatorname{sgn}(\sigma \tau) = \operatorname{sgn}(\sigma) \operatorname{sgn}(\tau)$

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



# Superlearn

- Q: Solve $\sigma^2 = (1 \ 2 \ 3)(4 \ 5 \ 6)$.

- Q: Compute $\sigma^2019$
A: Disjoint cycles decomposition, then $(1 \ \ldots \ n)^k = ()()()$ --- it breaks into $\frac{n}{\operatorname{gcd}(n, k)}$ parts, with $\operatorname{gcd}(n, k)$ elements in each part. 

- Q: <https://en.wikipedia.org/wiki/Vandermonde_matrix>

- Q: How to solve $x^2 = \sigma$?

- Q: Every $n$-cycle can be expressed as product of $n−1$ transpositions.

- Q: How to find parity of a permutation?
A: Using disjoing cycles, using decremtn.

- Q: Solve $(1 \  2) \sigma (3 \  4) = ((1\ 2\ 3)(4\ 5))^17$.

- Q: prove that permutations conjugate [$]\iff[/$] they have the same cycle structure
A:
   [$]\boxed{\Rightarrow}[/$]

   [$]\sigma(i) = k[/$]
   [$]\left(\pi \sigma \pi^{-1}\right) \left(\pi(i)\right) = \pi(k)[/$]  
 

   e.g.
   [$]\pi \ \cdot \ \begin{pmatrix}1 & 2 & 3\end{pmatrix} \begin{pmatrix} 4 & 5\end{pmatrix} \ \cdot \ \pi^{-1} \ = \ \left( \begin{smallmatrix}\pi(1) & \pi(2) & \pi(3)\end{smallmatrix} \right) \left( \begin{smallmatrix}\pi(4) & \pi(5)\end{smallmatrix}  \right)[/$]

   [$]\boxed{\Leftarrow}[/$]

   we can easily get conjugating permutation of two permutations with same structure
   by just writing one under another


[latex]
   \begin{align*}
   \sigma &= \begin{pmatrix}1 & 2 & 3\end{pmatrix} \begin{pmatrix}4 & 5\end{pmatrix} \\
   \pi \sigma \pi^{-1} &= \begin{pmatrix}1 & 5 & 2\end{pmatrix} \begin{pmatrix}3 & 4\end{pmatrix} \\
   \\
   \Rightarrow \pi &=  \begin{pmatrix}2 & 5 & 4 & 3\end{pmatrix}
   \end{align*}
[/latex]



<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- permutations">
    <p>Your browser does not support iframes.</p>
</iframe>

multiply permutations [$$]\begin{pmatrix} 1 &amp; 2 &amp; 3 &amp; 4 &amp; 5 &amp; 6 \\ 3 &amp; 5 &amp; 1 &amp; 6 &amp; 2 &amp; 4 \end{pmatrix} \cdot \begin{pmatrix} 1 &amp; 2 &amp; 3 &amp; 4 &amp; 5 &amp; 6 \\ 6 &amp; 3 &amp; 4 &amp; 2 &amp; 1 &amp; 5 \end{pmatrix} \ = \ ?[/$$]
[$$](\tau \sigma)(i) = \tau (\sigma (i)) = \begin{pmatrix} 1 &amp; 2 &amp; 3 &amp; 4 &amp; 5 &amp; 6 \\ 3 &amp; 5 &amp; 1 &amp; 6 &amp; 2 &amp; 4 \end{pmatrix} \cdot \begin{pmatrix} 1 &amp; 2 &amp; 3 &amp; 4 &amp; 5 &amp; 6 \\ 6 &amp; 3 &amp; 4 &amp; 2 &amp; 1 &amp; 5 \end{pmatrix} = \begin{pmatrix} 1 &amp; 2 &amp; 3 &amp; 4 &amp; 5 &amp; 6 \\ 4 &amp; 1 &amp; 6 &amp; 5 &amp; 3 &amp; 2 \end{pmatrix} \ \ \ \ \ \ \ \ \ (\text{right to left: } 1 \to 6 \to 4)[/$$]
algebra example permutations

write the permutation as a product of disjoint cycles<div><br /></div><div>[$$]\begin{pmatrix} 1 &amp; 2 &amp; 3 &amp; 4 &amp; 5 &amp; 6 &amp; 7 \\ 5 &amp; 4 &amp; 1 &amp; 7 &amp; 3 &amp; 6 &amp; 2 \end{pmatrix}[/$$]</div>
[$$]\begin{pmatrix} 1 &amp; 2 &amp; 3 &amp; 4 &amp; 5 &amp; 6 &amp; 7 \\ 5 &amp; 4 &amp; 1 &amp; 7 &amp; 3 &amp; 6 &amp; 2 \end{pmatrix} = \begin{pmatrix} 1 &amp; 5 &amp; 3 \end{pmatrix} \begin{pmatrix} 2 &amp; 4 &amp; 7 \end{pmatrix} = \begin{pmatrix} 1 &amp; 5 &amp; 3 \end{pmatrix} \begin{pmatrix} 2 &amp; 4 &amp; 7 \end{pmatrix} \begin{pmatrix} 6 \end{pmatrix} = \begin{pmatrix} 2 &amp; 4 &amp; 7 \end{pmatrix} \begin{pmatrix} 1 &amp; 5 &amp; 3 \end{pmatrix} = \begin{pmatrix} 2 &amp; 4 &amp; 7 \end{pmatrix} \begin{pmatrix} 1 &amp; 5 &amp; 3 \end{pmatrix} \begin{pmatrix} 6 \end{pmatrix}[/$$]
algebra example permutations

permutations:<div><br /></div><div>what is cycle and what is transposition?</div>
<div>cycle --- [$]\begin{pmatrix} 1 &amp; 2 &amp; 5 &amp; 6 \end{pmatrix}[/$]</div><div>transposition --- cycle of length two: [$]\begin{pmatrix}3 &amp; 4 \end{pmatrix}[/$]</div><div><br /></div>
algebra example permutations

multiply permutations:<div><br /></div><div>[$$]\left[\begin{pmatrix} 1 &amp; 3 &amp; 5 \end{pmatrix} \begin{pmatrix} 2 &amp; 4 &amp; 6 &amp; 7 \end{pmatrix}\right] \ &nbsp;\cdot \ \left[\begin{pmatrix} 1 &amp; 4 &amp; 7 \end{pmatrix} \begin{pmatrix} 2 &amp; 3 &amp; 5 &amp; 6 \end{pmatrix}\right] \ = \ \ ?[/$$]</div>
<div>[$$]\left[\begin{pmatrix} 1 &amp; 3 &amp; 5 \end{pmatrix} \begin{pmatrix} 2 &amp; 4 &amp; 6 &amp; 7 \end{pmatrix}\right] \ &nbsp;\cdot \ \left[\begin{pmatrix} 1 &amp; 4 &amp; 7 \end{pmatrix} \begin{pmatrix} 2 &amp; 3 &amp; 5 &amp; 6 \end{pmatrix}\right] = \begin{pmatrix} 1 &amp; 6 &amp; 4 &amp; 2 &amp; 5 &amp; 7 &amp; 3 \end{pmatrix}[/$$]</div><div><br /></div><div><br /></div><div><br /></div><div><div>[latex]<div>\begin{align*}</div><div>1 \to 4 \to 6&amp;: \ \ \ \begin{pmatrix} 1 &amp; 6 &amp; \ldots \end{pmatrix} \\</div><div>6 \to 2 \to 4&amp;: \ \ \ \begin{pmatrix} 1 &amp; 6 &amp; 4 &amp; \ldots \end{pmatrix} \\</div><div>4 \to 7 \to 2&amp;: \ \ \ \begin{pmatrix} 1 &amp; 6 &amp; 4 &amp; 2 &amp; \ldots \end{pmatrix}</div><div>\end{align*}</div>[/latex]</div></div>
algebra example permutations

<div>is the permutation even or odd?</div><div><br /></div><div>[$$]\begin{pmatrix} 1 &amp; 2 &amp; 3 &amp; 4 &amp; 5 &amp; 6 &amp; 7 \\ 5 &amp; 6 &amp; 4 &amp; 7 &amp; 2 &amp; 1 &amp; 3 \end{pmatrix}[/$$]</div>
<div>inversion is a pair of elements [$](x, \, y)[/$] such that [$]x &lt; y[/$] and [$]\sigma(x) &gt; \sigma(y)[/$]</div><div><br /></div><div>let's count inversions</div><div><br /></div><div>[$]\sigma(1) &gt; \sigma(3),\,\sigma(5),\,\sigma(6),\,\sigma(7)[/$]</div><div><div>[$]\sigma(2) &gt; \ldots[/$]</div><div>...</div><div>&nbsp;&nbsp;</div><div>[$]\Updownarrow[/$]</div></div><div><br /></div><div>5 &gt; 4,2,1,3 --- 4 inversions</div><div>6 &gt; 4,2,1,3 --- 4 inversions</div><div>4 &gt; 2,1,3 --- 3 inversions</div><div>7 &gt; 2,1,1 --- 3 inversions</div><div>2 &gt; 1 --- 1 inversion</div><div>&nbsp;&nbsp;</div><div><br /></div><div>4 + 4 + 3 + 3 + 1 = 15 --- the permutation is odd</div>
algebra example permutations

<div>is the permutation even or odd?</div><div><br /></div><div>[$$]\begin{pmatrix} 1 &amp; 2 &amp; 3 &amp; 4 &amp; 5 &amp; 6 &amp; 7 \\ 5 &amp; 6 &amp; 2 &amp; 7 &amp; 4 &amp; 1 &amp; 3 \end{pmatrix}[/$$]</div>
<div>inversion is a pair of elements [$](x, \, y)[/$] such that [$]x &lt; y[/$] and [$]\sigma(x) &gt; \sigma(y)[/$]</div><div><br /></div><div>let's count inversions</div><div><br /></div><div>[$]\sigma(1) &gt; \sigma(3),\,\sigma(5),\,\sigma(6),\,\sigma(7)[/$]</div><div>[$]\sigma(2) &gt; \ldots[/$]</div><div>...</div><div>&nbsp;&nbsp;</div><div>[$]\Updownarrow[/$]</div><div><br /></div><div><div>5 &gt; 2,4,1,3 --- 4 inversions</div><div>6 &gt; 2,4,1,3 --- 4 inversions</div><div>2 &gt; 1 --- 1 inversion</div><div>7 &gt; 4,1,3 --- 3 inversions</div><div>4 &gt; 1,3 --- 2 inversions</div><div>&nbsp;&nbsp;</div><div>4 + 4 + 1 + 3 + 2 = 14 --- the permutation is even</div></div><div><br /></div>
algebra example permutations

get the inversed permutation:<div><br /></div><div>[$$]\begin{pmatrix} 1 &amp; 2 &amp; 3 &amp; 4 &amp; 5 \\ 2 &amp; 5 &amp; 4 &amp; 3 &amp; 1 \end{pmatrix}^{-1}[/$$]</div>
<div>to inverse a permutation just interchange the two lines:</div><div><br /></div><div>[$$]<div>\begin{pmatrix} 1 &amp; 2 &amp; 3 &amp; 4 &amp; 5 \\ \boldsymbol 2 &amp; \boldsymbol 5 &amp; \boldsymbol 4 &amp; \boldsymbol 3 &amp; \boldsymbol 1 \end{pmatrix}^{-1}</div><div>&nbsp; &nbsp; &nbsp; =\begin{pmatrix} \boldsymbol 2 &amp; \boldsymbol 5 &amp; \boldsymbol 4 &amp; \boldsymbol 3 &amp; \boldsymbol 1 \\ 1 &amp; 2 &amp; 3 &amp; 4 &amp; 5 \end{pmatrix}</div><div>&nbsp; &nbsp; &nbsp; =\begin{pmatrix} 1 &amp; 2 &amp; 3 &amp; 4 &amp; 5 \\ 5 &amp; 1 &amp; 4 &amp; 3 &amp; 2\end{pmatrix}</div>[/$$]</div>
algebra example permutations

what is the parity of cycle<div><br /></div><div>[$]\begin{pmatrix} 1 &amp; 2 &amp; \ldots &amp; n \end{pmatrix}[/$]</div>
<div><div>the sign is [$](-1)^{n-1}[/$] since there are [$](n-1)[/$] transpositions:</div></div><div><br /></div><div><br /></div><div><br /></div><div>[$]\begin{pmatrix} 1 &amp; 2 &amp; \ldots &amp; n \end{pmatrix} = \begin{pmatrix} 1 &amp; n \end{pmatrix} \cdot \begin{pmatrix} 1 &amp; n-1 \end{pmatrix} \cdot \ldots \cdot \begin{pmatrix} 1 &amp; 3 \end{pmatrix} \cdot \begin{pmatrix} 1 &amp; 2 \end{pmatrix}[/$]</div>
algebra example permutations

definition of <i>parity</i> of a permutation
<div>two equivalent definitions based on:</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><i>number of inversions</i></div><div><br /></div><div><i>number of transpositions</i></div><div><br /></div><div><br /></div>
algebra definition permutations

how does multiplying a permutation by transposition affects the parity?
it will change the sign
algebra example permutations

definition of order of a permutation
order of [$]\sigma[/$]&nbsp;is the least positive integer [$]m[/$] such that [$]\sigma^m=1[/$]<div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>if the permutation is written as a product of disjoint cycles, then it's order is the LCM of the lengths of it's cycles</div>
algebra definition permutations

how to get number of inversions in an array in [$]O(n \log n)[/$]
merge sort<div><br /></div><div><br /></div><div>the number of&nbsp;inversions removed while merging is the number of elements left from the the left array to be merged</div>
algebra algorithm permutations

do even permutations or odd permutations form a subgroup of [$]S_n[/$]?
<div>even permutations form a subgroup of [$]S_n[/$]</div><div><br /></div><div><br /></div><div>odd permutations cannot form a subgroup, since the composite of two odd permutations is even</div>
algebra example permutations

prove that any even permutation can be written as a product of cycles of length three
even permutation can be written as a product of even number transpositions<div><br /></div><div><div>(i j)(k l) = (i j l) when j=k</div><div>otherwise, (i j)(k l) = (i j)(j k) (j k)(k l) = (i j k)(j k l)</div></div>
algebra example permutations

prove that any even permutation can be written as a product of these cycles: (1 2 3), (1 2 4), ... , (1 2 n)
any even permutation can be written as a product of cycles of length three: (a k l)<div><br /></div><div>(1 k l) = (1 2 l) (1 2 k)^2</div><div><br /></div><div><div>just like the above: (a k l) = (a 2 l) (a k 2)&nbsp;= (2 l a) (2 a k)</div></div><div>and interchange 2 and 1 in (2 l a) and (2 a k)</div>
algebra example permutations

write this cycle as a product of transpositions<br /><div><br /></div><div><div>[$]\begin{pmatrix} 1 &amp; 2 &amp; \ldots &amp; n \end{pmatrix}[/$]</div></div>
<div>[$]\begin{pmatrix} 1 &amp; 2 &amp; \ldots &amp; n \end{pmatrix} = \begin{pmatrix} 1 &amp; n \end{pmatrix} \cdot \begin{pmatrix} 1 &amp; (n-1) \end{pmatrix} \cdot \ldots \cdot \begin{pmatrix} 1 &amp; 3 \end{pmatrix} \cdot \begin{pmatrix} 1 &amp; 2 \end{pmatrix}[/$]</div><div>and also</div><div>[$]\begin{pmatrix} 1 &amp; 2 &amp; \ldots &amp; n \end{pmatrix} = \begin{pmatrix} 1 &amp; 2 \end{pmatrix} \cdot \begin{pmatrix} 2 &amp; 3 \end{pmatrix} \cdot \ldots \cdot \begin{pmatrix} {n-1} &amp; n \end{pmatrix}[/$]</div>
algebra example permutations

how to get the parity of a permutation if it's written as a product of disjoint cycles?
<div><div>[$]\sigma = c_1 \cdot \ldots \cdot c_n[/$]</div><div>[$]\operatorname{sgn} \sigma = (-1)^{\operatorname{parity}(c_1) + \ldots + \operatorname{parity}(c_n)}[/$]</div></div>
algebra permutations

get inverted cycle<div><br /></div><div>[$]\begin{pmatrix} i_1 &amp; \ldots &amp; i_n \end{pmatrix}^{-1}[/$]</div>
[$]\begin{pmatrix} i_1 &amp; \ldots &amp; i_n \end{pmatrix}^{-1} = \begin{pmatrix} i_n &amp; \ldots &amp; i_1 \end{pmatrix}[/$]
algebra example permutations

prove that number of even permutations is the same as number of odd permutations
multiply an even permutation by a transposition and get an odd one, this defines a bijection
algebra example permutations

prove that any permutation can be written as a product of these cycles: (1 2), (1 2 3 ... n)
<div>(1 2 3 ... n)^1 (1 2) (1 2 3 ... n)^{-1} = (2 3)</div><div>(1 2 3 ... n)^k (1 2) (1 2 3 ... n)^{-k} = (k+1 k+2)</div><div><br /></div><div>now we have (1 2), (2 3), (3 4), ... , (n-1 n)</div><div>(3 7) &nbsp;= &nbsp;(3 4) (4 5) (5 6) (6 _7_) &nbsp; (6 5) (5 4) (4 3)</div><div><br /></div><div>now we have all transpositions</div>
algebra example permutations

find number of permutations in [$]S_{10}[/$] that commute with&nbsp;(1 3 5 7 9)
<div>&nbsp; &nbsp; &nbsp;[$]\rho \tau = \tau \sigma \iff \rho = \tau \sigma \tau^-1[/$]</div><div>&nbsp; &nbsp; &nbsp;permutations conjugate [$]\iff[/$] they have the same cycle structure</div><div>&nbsp; &nbsp; &nbsp;i.e. they consist of [$]n_1[/$] cycles of length [$]l_1[/$], ... , [$]n_k[/$] cycles of length [$]l_k[/$]</div><div>&nbsp; &nbsp; &nbsp;(1 2 3)(4 5)(6)(7)</div><div>&nbsp; &nbsp; &nbsp;(1 5 2)(3 4)(7)(6)</div><div>&nbsp; &nbsp; &nbsp;</div><div>&nbsp; &nbsp; &nbsp;</div><div>&nbsp; &nbsp; &nbsp;</div><div>&nbsp; &nbsp; &nbsp;</div><div>&nbsp; &nbsp; &nbsp;now, how many permutations [$]\tau[/$] such that [$]\rho = \sigma = \tau \sigma \tau^-1[/$]?</div><div>&nbsp; &nbsp; &nbsp;</div><div>&nbsp; &nbsp; &nbsp;the permutations in [$]S_6[/$] that commute with (123)(456) will either map&nbsp;</div><div>&nbsp; &nbsp; &nbsp;(123) and (456) to themselves or interchange them</div><div>&nbsp; &nbsp; &nbsp;because disjoint cycles commute</div><div>&nbsp; &nbsp; &nbsp;</div><div>&nbsp; &nbsp; &nbsp;giving total [$]3^2 \cdot 2![/$] different permutations [$]\tau[/$] that commute with our (1 2 3)(4 5 6)</div><div>&nbsp; &nbsp; &nbsp;</div><div><br /></div><div>&nbsp; &nbsp; &nbsp;[$]\sigma \ = \ &nbsp;\prod \ n_i \ &nbsp;\text{cycles of length} \ &nbsp;l_i[/$]</div><div>&nbsp; &nbsp; &nbsp;then the centralizer</div><div>&nbsp; &nbsp; &nbsp;[$]|C_\sigma| \ &nbsp;= \ &nbsp;\prod {l_i}^{n_i} \, {n_i}![/$]</div>
algebra example permutations

prove that&nbsp;permutations conjugate [$]\iff[/$] they have the same cycle structure
<div>&nbsp; &nbsp;[$]\boxed{\Rightarrow}[/$]</div><div><br /></div><div>&nbsp; &nbsp;[$]\sigma(i) = k[/$]</div><div>&nbsp; &nbsp;[$]\left(\pi \sigma \pi^{-1}\right) \left(\pi(i)\right) = \pi(k)[/$] &nbsp;</div><div>&nbsp;</div><div><br /></div><div>&nbsp; &nbsp;e.g.</div><div>&nbsp; &nbsp;[$]\pi \ \cdot \ \begin{pmatrix}1 &amp; 2 &amp; 3\end{pmatrix} \begin{pmatrix} 4 &amp; 5\end{pmatrix} \ \cdot \ \pi^{-1} \ = \ \left( \begin{smallmatrix}\pi(1) &amp; \pi(2) &amp; \pi(3)\end{smallmatrix} \right) \left( \begin{smallmatrix}\pi(4) &amp; \pi(5)\end{smallmatrix} &nbsp;\right)[/$]</div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;</div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div><br /></div><div>&nbsp; &nbsp;[$]\boxed{\Leftarrow}[/$]</div><div><br /></div><div>&nbsp; &nbsp;we can easily get conjugating permutation of two permutations with same structure</div><div>&nbsp; &nbsp;by just writing one under another</div><div><br /></div><div><br /></div><div>[latex]</div><div>&nbsp; &nbsp;\begin{align*}</div><div>&nbsp; &nbsp;\sigma &amp;= \begin{pmatrix}1 &amp; 2 &amp; 3\end{pmatrix} \begin{pmatrix}4 &amp; 5\end{pmatrix} \\</div><div>&nbsp; &nbsp;\pi \sigma \pi^{-1} &amp;= \begin{pmatrix}1 &amp; 5 &amp; 2\end{pmatrix} \begin{pmatrix}3 &amp; 4\end{pmatrix} \\</div><div>&nbsp; &nbsp;\\</div><div>&nbsp; &nbsp;\Rightarrow \pi &amp;= &nbsp;\begin{pmatrix}2 &amp; 5 &amp; 4 &amp; 3\end{pmatrix}</div><div>&nbsp; &nbsp;\end{align*}</div><div>[/latex]</div>
algebra permutations

write (2 5) using transpositions (1 2), (2 3), (3 4), ..., (n-1 n)
(2 5) &nbsp; = &nbsp; (2345) &nbsp; (234)^{-1} &nbsp; = &nbsp; (2 3) (3 4) (4 5) &nbsp; (4 3) (3 2)
algebra example permutations

