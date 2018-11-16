---
title:  "Discrete math"
layout: default

---

* this line gets replaced with the generated table of contents
{:toc}

# Logic

<https://en.wikipedia.org/wiki/Truth_table>

If any doubts, draw a table and check it yourself. 

$\neg(\neg x) = x$
commutativity
associativity
distributivity of $\vee, \wedge$: $(x \wedge y) \vee z = (x \wedge z) \vee (y \wedge z)$, $(x \vee y) \wedge z = (x \wedge z) \vee (y \wedge z)$
$\neg (x \vee y) = \neg x \wedge \neg y$, $\neg (x \wedge y) = \neg x \vee \neg y$
$x \vee \neg x = 1$
$x = x \vee 0 = x \wedge 1 = x \oplus 0$, $x \wedge 0 = 0$, $x \oplus 1 = \neg x$
idempotence: $x = x \vee x = x \wedge x = x \rightarrow x$
absorbtion: $(x \vee y) \wedge x = x$, $(x \wedge y) \vee x = x$
$x \rightarrow y = \neg x \vee y = \neg (x \wedge \neg y) = 1 \oplus x \oplus xy$, $x \oplus y = (x \wedge \neg y) \vee (\neg x \wedge y) = (x \vee y) \wedge (\neg x \vee \neg y)$

- Q: ^ --- should just memorize those

- Q: Express:
  - $\vee, \wedge, \neg$ using $\neg, \rightarrow$
  - $\vee, \wedge, \neg$ using $1, \wedge, \oplus$
  - $\vert$ and $\downarrow$ using $\vee, \wedge, \neg$ --- $A \vert B \ = \ \neg (A \wedge B)$, $A \downarrow B \ = \ \neg (A \vee B)$
  - $\vee, \wedge, \neg$ using $\vert$; using $\downarrow$ --- 
  - prove there are no single operation that can be used to express $\vee, \wedge, \neg$



## Implication

- $x \rightarrow y$ can be paraphrased to "if $x$, then it can't be not $y$". "It's raining" $\rightarrow$ "ground is wet". If it's raining, the ground can't be not wet. $x \rightarrow y = \neg (x \wedge \neg y)$.
Same thing: $(x < 3) \rightarrow (x < 5)$. If $(x < 3)$, it can't be that it's not $(x < 5)$.

- "If you are a man, you'll do this". $x \rightarrow y = \neg x \vee y$. You're not a man or you'll do this.

$0 \rightarrow 1$ doen't mean that we can infer truth from false.
It only means we can have a situation when premise is false and conclusion is still true anyway. Like $x \ge 3$, but it's still $x < 5$.
A legit theorem can have a wrong proof.


properties of implication (these are $= 1$):
$x \rightarrow x$
$(x \rightarrow y) \wedge (y \rightarrow x)$
$((x \rightarrow y) \wedge (y \rightarrow z)) \rightarrow (x \rightarrow z)$
$((x \rightarrow y) \vee (x \rightarrow \neg y)) \rightarrow \neg x$
$((x \rightarrow y) \wedge x) \rightarrow y$
Interesting thing: $\neg p \rightarrow (p \rightarrow q)$.

# Sets

Russel's paradox
universal set
    
operations on sets, proof of formulas like (A v B) C = AC v BC
    
logic tables: -, or, xor, and, ->, ≡
A -> B = -A v B
(A -> B) v (B -> A) = A≡B
((A->B) * (B->)) -> (A->C)


TODO: logic tables and formulas for for must have equations

<https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#tables>, <https://www.tablesgenerator.com/markdown_tables#>

| A | B | A->B |
|---|---|------|
| 0 | 0 | 1  |
| 0 | 1 | 1  |
| 1 | 0 | 0  |
| 1 | 1 | 1  |

<https://en.wikipedia.org/wiki/Indicator_function>

<https://en.wikipedia.org/wiki/Inclusion%E2%80%93exclusion_principle>


$\vert A \cup B \vert = \vert A \vert + \vert B \vert - \vert A \cap B \vert$
$\vert A \cup B \cup C \vert = \vert A \vert + \vert B \vert + \vert C \vert - \vert A \cap B \vert - \vert A \cap C \vert - \vert B \cap C \vert + \vert A \cap B \cap C \vert$


$$
{\begin{aligned}\left\vert \bigcup _{i=1}^{n}A_{i} \right\vert ={}&\sum _{i=1}^{n} \vert A_{i} \vert - \sum_{1\leq i<j\leq n} \vert A_{i} \cap A_{j} \vert + \dots {}\\&{}\dots +\sum _{1\leq i<j<k\leq n}\vert A_{i}\cap A_{j}\cap A_{k}\vert -\dots +(-1)^{n-1}\left\vert A_{1}\cap \dots \cap A_{n}\right\vert .\end{aligned}}
$$

$$
{\displaystyle \left\vert \bigcup_{i=1}^{n}A_{i} \right\vert = \sum_{k=1}^{n}(-1)^{k+1}\left(\sum_{1\leq i_{1}<\cdots <i_{k}\leq n} \vert A_{i_{1}}\cap \cdots \cap A_{i_{k}} \vert \right)}
$$

minimal set of ops: v, *, -; proof

<https://en.wikipedia.org/wiki/Disjunctive_normal_form>




# Post's theorem on function completeness

- Truth-preserving <span markdown="0">$T_0 = \left\{ \, f \ : \ f(0,\dots ,0) = 0 \, \right\}$</span>, $\vee ,\wedge ,\top ,\rightarrow ,\leftrightarrow$
- False-preserving <span markdown="0">$T_1 = \left\{ \, f \ : \ f(1,\dots ,1) = 1 \, \right\}$</span>, $\vee ,\wedge ,\bot ,\nrightarrow ,\nleftrightarrow$
- Monotonic <span markdown="0">$M = \left\{ \, f \ : \ \forall i(a_{i}\leq b_{i}) \ \ f(a_{1},\dots ,a_{n})\leq f(b_{1},\dots ,b_{n}) \, \right\}$</span>, $\vee ,\wedge ,\top ,\bot$; note they don't depend on order of variables
- Self-dual <span markdown="0">$S = \left\{ \, f \ : \ f(\overline {x_{1}},\dots ,\overline {x_{n}})=\overline {f(x_{1},\dots ,x_{n})} \, \right\}$</span>, $\neg $, $MAJ(p, q, r)$
- Linear <span markdown="0">$L = \left\{ \, f \ : \ f(x_{1},\dots ,x_{n})=a_{0}\oplus a_{1}x_{1}\oplus \dots \oplus a_{n}x_{n} \,  \right\}$</span> 

- Q: Prove closure of the sets: $T_0, T_1, M, S, L$.

```
Using non-false-preserving, non-monotonic, non-self-dual functions we get constants and invertor:

f not in T_0 ---> 1 ---> 0 
             \     \      \
              \     \---> ~x
               \
                \---> ~x ---> 0
                        \      \
                         \----> 1

Now we have 0, 1, ~x, non-linear f   -->   we have xy   -->   we have x+y   -->   we have everything 
```

- Q: Prove these steps in proof of Post's functional completeness theorem:
  - We have $f \notin T_0$, then we have either $1$, or $\neg x$.
  - We have $f \notin T_1$, then we have either $0$, or $\neg x$.
  - We have $\neg x$ and $f \notin S$, then we have either $0$, or $1$.
  - We have $0, 1, f \notin M$, then we have $\neg x$.
  - And finally, we have $0, 1, \neg x, f \notin L$, how to get $x \cdot y$?
- A: 

- Q: Weak functonal completeness???, hw2p56.



<https://ru.wikipedia.org/wiki/Критерий_Поста>
<https://en.wikipedia.org/wiki/Functional_completeness>
<https://www.academia.edu/12708709/Posts_functional_completeness_theorem>
<https://en.wikipedia.org/wiki/Post%27s_lattice>
Clones of closed classes, proof of equivalence of some of them: 1, `\oplus`, `\wedge`
class of monotonic functions and algorithm of checking it: <https://ido.tsu.ru/iop_res/bulevfunc/text/g15_5.html>

<https://en.wikipedia.org/wiki/Sheffer_stroke>
Peirce's arrow $\downarrow$: <https://en.wikipedia.org/wiki/Logical_NOR>


<https://ru.wikipedia.org/wiki/Полином_Жегалкина>
<https://en.wikipedia.org/wiki/Zhegalkin_polynomial>
Proof of uniqueness and existence of Zhegalkin polynomial, not from wikipedia, it's cheating.
<https://neerc.ifmo.ru/wiki/index.php?title=Полином_Жегалкина#.D0.A1.D1.83.D1.89.D0.B5.D1.81.D1.82.D0.B2.D0.BE.D0.B2.D0.B0.D0.BD.D0.B8.D0.B5_.D0.B8_.D0.B5.D0.B4.D0.B8.D0.BD.D1.81.D1.82.D0.B2.D0.B5.D0.BD.D0.BD.D0.BE.D1.81.D1.82.D1.8C_.D0.BF.D1.80.D0.B5.D0.B4.D1.81.D1.82.D0.B0.D0.B2.D0.BB.D0.B5.D0.BD.D0.B8.D1.8F_.28.D1.82.D0.B5.D0.BE.D1.80.D0.B5.D0.BC.D0.B0_.D0.96.D0.B5.D0.B3.D0.B0.D0.BB.D0.BA.D0.B8.D0.BD.D0.B0.29>
Method of computation.
`не` не может быть выражена через набор `или`, `и`
There are $2^{2^n}$ functions of $n$ variables.

Monotone functions order? <https://en.wikipedia.org/wiki/Hasse_diagram>, n-dimentional cube
Класс функций называется функционально полным в слабом смысле, если добавление в и констант 0 и 1 превращает его в функционально полный класс.

композиция монотонных функций монотонна
линейный полином жегалкина



- Q: How to check if a function is truth-preserving, false-preserving, self-dual, monotone (number of options to check?), linear?
A cube for checking a function with three variables.
The method of indeterminate coefficients: <https://wikimatik.ru/article/36>, <https://en.wikipedia.org/wiki/Zhegalkin_polynomial#The_method_of_indeterminate_coefficients>

- Q: What is the max number of functions in a basis of functionally complete set? --- A: Theorem. Max number of functions in basis is 4: <https://ru.wikipedia.org/wiki/Критерий_Поста#Теорема_о_максимальном_числе_функций_в_базисе>
- Q: Why are there only five classes? --- A: Because otherwise it would have a function ouside of those $T_0, T_1, M, S, L$ classes and be complete according to the Post's theorem.

полная в слабом смысле --- <http://matica.org.ua/metodichki-i-knigi-po-matematike/lektcii-po-diskretnoi-matematike/2-3-3-teoremy-o-funktcionalnoi-polnote>

expressing functions from each other --- <http://www.calcsbox.com/post/bulevy-funkcii-ot-odnogo-i-dvuh-argumentov.html#toc6>


- Q: Prove that it's impossible to express:
  - $\neg$ using $\vee, \wedge$
  - $\vee, \wedge$ usign $\neg, \equiv$
  - $\wedge$ usign $\vee, \rightarrow$
  
- Q: 
  - Find all truth-preserving and false-preserving functions with two variables.
  - Prove number of truth-preserving functions is equal to number of false-preserving functions.

- Q:
  - How many functions with $n$ variables are there?
  - How many linear?
  - How many self-dual?
  - How many truth-preserving, false-preserving?
  - How many monotone? --- this question wasn't in the list
  
- Q: Prove that if $f$ is self-dual, then $\neg f$ is also self-dual.
- Q: 
  - Prove there are no self-dual functions that depend (significantly) on exactly two variables.
  - Find all self-dual functions that significantly depend on three variables.
  - Prove a linear function is self-dual $\Leftrightarrow$ it significantly depends on an odd number of variables.
  
- Q: 
  - Find a linear function (Zhegalkin polynomial) for functions with 3 variables that is true only on inputs with prime indices.
  - Same with 4 variables. How to use the previous result to find it?
  
- Q: hw2p49 --- Let $f$ a non-constant function. Prove that in it's truth-table:
  - there is an even number of ones.
  - number of ones is equal to number of zeros.

- Q: hw2p50 --- Prove any monotone function can be expressed using $0, 1, \vee, \wedge$.

- Q: Are the following sets of functions complete?
  - $\vee, \wedge, \oplus$
  - $\vee, \wedge, x \oplus y \oplus z \oplus 1$
  - $1, \neg x, x \equiv y$
  - $0, \neg x, x (y \oplus z) \oplus yz$
  - $1, xy (x \oplus z)$
  - $\leftarrow, \oplus$
  
- Q: Let $p(n)$ number of functions with $n$ variables, that alone constitute functionally complete systems.
$$
\lim_{n \rightarrow \inf}\frac{p(n)}{2^{2^n}} \ = \ ?
$$


## dual functions

$(x \vee y)* = $
$(x \wedge y)* = $
$(x \oplus y)* = x \oplus y \oplus 1$

- Q: Is dual to a linear function linear?
- Q: How to test for self-dualness?


# Problems

HW.01.05. $A = \{ 1, 2, 4, 5, 9 \}$, $B = \{ 2, 3, 5, 6, 9 \}$, $C = \{ 4, 5, 6, 7 \}$. Express $\{4, 5, 7\}$ and $\{1, 2, 4\}$ through A, B, C.
How to prove the latter can't be expressed?
--- Если входит 2, то по там же причинам должна входить и 9 - делаются те же проверки.

HW.01.07. Write an equation which has set of solutions equal to _intersection_ of solution sets of equations <span markdown="0">$\sin x = \vert \sin x \vert$ and $\cos x = \tan{\tan x}$</span>.
- Q: What equation $u(f, g)=0$ has solution set that is _union_ of solution sets of $f=0$ and $g=0$? _Intersection_?
$u(f, g) = 0 \Leftrightarrow f=0, g=0$
$u=f^2+g^2$

HW.01.09.
HW.01.10.

HW.01.16. When proving set A is equal to set B, we have to prove $A \in B$ and $B \in A$.


- Q: When are two sets equal? --- A: $A = B$ when $A \subseteq B$ and $B \subseteq A$.
- Q: How many subsets does a set of $n$ elements have? --- A: $2^n$
- Q: Is it true that 1) a set, that only has an empty set as it's element, is a subset of an empty set? 2) It's equal to set of all subsets of an empty set? --- A:
- Q: Prove $(A \cap B) \setminus C \ = \ (A \setminus C) \cap$.

- Q: Prove distributivity law: $A \cap (B \cup C) \ = \ (A \cap B) \cup (A \cap C)$, $A \cup (B \cap C) \ = \ (A \cup B) \cap (A \cup C)$
And absorbtion law: $(A \cup B) \cap A \ = \ A$, $(A \cap B) \cup A \ = \ A$
- A: <https://math.stackexchange.com/questions/239464/math-proof-of-absorption-law>

- Q: Prove these properties of compliment:
  - Double compliment law: $\overline{\overline A} = A$
  - $A \subseteq B \ \Rightarrow \ \overline B \subseteq \overline A$
  - De Morgan's law: $\overline {A \cup B} \ = \ {\overline A} \cap {\overline B}$, $\overline {A \cap B} \ = \ {\overline A} \cup {\overline B}$
- A: <https://math.stackexchange.com/questions/937166/double-complement-of-a-set-proof>, <https://en.wikipedia.org/wiki/De_Morgan's_laws#Formal_proof> 

- Q: Prove the following properties of set difference:
  - $A \subseteq B \quad \Leftrightarrow \quad A \setminus B \ = \ \emptyset$
  - $A \setminus B \ = \ B \setminus A \quad \Leftrightarrow \quad A \ = \ B$ (anticommutativity)
  - $(A \setminus B) \setminus C \ = \ (A \setminus C) \setminus (B \setminus C)$ (self-distributivity)
  - $A \setminus B \ = \ A \setminus (A \cap B)$
  - $A \setminus (B \setminus C) \ = \ (A \setminus B) \cup (A \cap C)$
  - $(A \setminus C) \setminus (B \setminus A) \quad \subseteq \quad (A \setminus C) \quad \subseteq \quad (A \setminus B) \cup (B \setminus C)$

- Q: properties of $\subseteq$
  - $A \subseteq B \quad \Leftrightarrow \quad A \cup B = B$
  - $A \subseteq B \quad \Leftrightarrow \quad A \cap B = A$

- Q: Properties of set difference $\triangle$:
  - It's commutative, associative.
  - $A = B \quad \Leftrightarrow \quad A \triangle B = \emptyset$
  - $A \triangle B = C \quad \Leftrightarrow \quad A \triangle C = B \quad \Leftrightarrow \quad B \triangle C = A$
  - $A \cap B = \emptyset \quad \Leftrightarrow \quad A \cup B = A \triangle B$
  - $A \cup B \ = \ (A \triangle B) \triangle (A \cap B)$
  - $A \setminus B \ = \ A \triangle (A \cap B)$

- Q: Prove properties of set compliment:
  - Set compliment $B$ for $A$ is fully defined from these two conditions: $A \cup A^C = U$ and $A \cap A^C = \emptyset$.

- Q: $A \cap B = \emptyset \quad \Leftrightarrow \quad B \subseteq \overline A$.

- Q: Express set difference $\setminus$ using:
  - intersection and compliment
  - union and compliment

- Q: Prove properties of $\subseteq$:
  - $A \subseteq B \quad \Leftrightarrow \quad A \cup B = B$
  - $A \subseteq B \quad \Leftrightarrow \quad A \cap B = A$
  - Let $A_1 \subseteq B_1$, $A_2 \subseteq B_2$:
    - $A_1 \cup B_1 \ \subseteq \ A_2\cup B_2$ --- stability against union
    - $A_1 \cap B_1 \ \subseteq \ A_2\cap B_2$ --- against intersection


# Indicator functions

$\chi_A(x) = 1$ when $x \in A$

- Q: Prove for finite $U$ and $A$: $\sum_{x \in U} \chi_A(x) = \vert A \vert$

- Q: Prove:
  - $\chi_{ A \cap B }(x) \ = \ \chi_A(x) \wedge \chi_B(x)$, there's a hint, hw2p28a
  - $\chi_{ A \cup B }(x) \ = \ \chi_A(x) \vee \chi_B(x)$
  - $\chi_{\overline A}(x) = \neg \chi_A(x) = 1 - \chi_A(x)$
  
- Q: Fill in the gaps:
  - $\chi_{A \setminus B} = \chi_A(x) \ldots \chi_B(x)$
  - $\chi_{A \ldots B} = \chi_A(x) \oplus \chi_B(x)$
  - $\chi_{A \ldots B} = \chi_A(x) \rightarrow \chi_B(x)$
  - $\chi_{A \ldots B} = \chi_A(x) \equiv \chi_B(x)$
  
- Q: hw2p31,32 --- Prove $\vert A \cup B \vert = \vert A \vert + \vert B \vert - \vert A \cap B \vert$
  Prove $\vert A \cup B \cup C \vert = \vert A \vert + \vert B \vert + \vert C \vert - \vert A \cap B \vert - \vert A \cap C \vert- \vert B \cap C \vert + \vert A \cap B \cap C \vert$
  Prove the inclusion-exclusion principle for arbitrary number of sets.
  <https://ru.wikipedia.org/wiki/Формула_включений-исключений#Доказательство>
  <https://en.wikipedia.org/wiki/Inclusion–exclusion_principle#Proof_of_main_statement>
  <https://en.wikipedia.org/wiki/Inclusion–exclusion_principle#Algebraic_proof>
  Prove $\vert A \triangle B \vert = \vert A \vert + \vert B \vert - 2 \vert A \cap B \vert$
  $\vert A \triangle B \triangle C \vert = \vert A \vert + \vert B \vert + \vert C \vert - 2 \left( \vert A \cap B \vert - \vert A \cap C \vert - \vert B \cap C \vert \right)+ \vert A \cap B \cap C \vert$
  \*Prove for arbitrary number of sets.

$$
\begin{aligned}
\chi_{A \cup B}(x) &= \chi_A(x) \vee \chi_B(x) = 1 - \overline{\chi_A(x) \vee \chi_B(x)} = \\
&= 1 - \overline{\chi_A(x)} \cdot \overline{\chi_B(x)} = \\
&= 1 - (1 - \chi_A(x)) \cdot (1 - \chi_B(x)) = \\
&= \chi_A(x) + \chi_B(x) - \chi_A(x) \cdot \chi_B(x)
\end{aligned}
$$

$$
\begin{aligned}
\vert A \cup B \vert &= \sum_{x \in U} \chi_{A \cup B}(x) = \sum_{x \in U} \left( \chi_A(x) + \chi_B(x) - \chi_A(x) \cdot \chi_B(x) \right) = \\
&= \sum_{x \in U} \chi_A(x) + \sum_{x \in U} \chi_B(x) + \sum_{x \in U} \chi_A(x) \cdot \chi_B(x) = \\
&= \sum_{x \in U} \chi_A(x) + \sum_{x \in U} \chi_B(x) + \sum_{x \in U} \chi_{A \cap B}(x) = \\
&= \vert A \vert + \vert B \vert - \vert A \cap B \vert
\end{aligned}
$$





<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- discrete math">
    <p>Your browser does not support iframes.</p>
</iframe>






