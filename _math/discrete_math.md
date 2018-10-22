---
title:  "Discrete math"
layout: default

---

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

$| A \cup B| = |A| + |B| - |A \cap B|$
$|A\cup B\cup C|=|A|+|B|+|C|-|A\cap B|-|A\cap C|-|B\cap C|+|A\cap B\cap C|$

$$
{\displaystyle {\begin{aligned}\left|\bigcup _{i=1}^{n}A_{i}\right|={}&\sum _{i=1}^{n}|A_{i}|-\sum _{1\leq i<j\leq n}|A_{i}\cap A_{j}|+\cdots {}\\&{}\cdots +\sum _{1\leq i<j<k\leq n}|A_{i}\cap A_{j}\cap A_{k}|-\cdots +(-1)^{n-1}\left|A_{1}\cap \cdots \cap A_{n}\right|.\end{aligned}}}
$$

$$
{\displaystyle \left|\bigcup _{i=1}^{n}A_{i}\right|=\sum _{k=1}^{n}(-1)^{k+1}\left(\sum _{1\leq i_{1}<\cdots <i_{k}\leq n}|A_{i_{1}}\cap \cdots \cap A_{i_{k}}|\right)}
$$

minimal set of ops: v, *, -; proof

<https://en.wikipedia.org/wiki/Disjunctive_normal_form>

# Logic

- Truth-preserving $T_{0} = \left\{ f \ | \ f(0,\dots ,0)=0 \right\}$, $\vee ,\wedge ,\top ,\rightarrow ,\leftrightarrow $
- False-preserving $T_{1} = \left\{ f \ | \ f(1,\dots ,1)=1 \right\}$, $\vee ,\wedge ,\bot ,\nrightarrow ,\nleftrightarrow$
- Monotonic $M = \left\{ f \ | \ \forall i(a_{i}\leq b_{i}) \ \ f(a_{1},\dots ,a_{n})\leq f(b_{1},\dots ,b_{n}) \right\}$, $\vee ,\wedge ,\top ,\bot$
- Self-dual $S = \left\{ f \ | \ f(\overline {x_{1}},\dots ,\overline {x_{n}})=\overline {f(x_{1},\dots ,x_{n})} \right\}$, $\neg $, $MAJ(p, q, r)$
- Linear $L = \left\{ f \ | \ f(x_{1},\dots ,x_{n})=a_{0}\oplus a_{1}x_{1}\oplus \dots \oplus a_{n}x_{n} \right\}$, 

<https://en.wikipedia.org/wiki/List_of_logic_symbols>

- Q: Why are there only two operations like up arrow and stroke? --- A: Build a truth table.

Post's Functional Completeness Theorem — <https://cs.hse.ru/data/2015/05/28/1096847873/Lecture 13.1.pdf>
<https://ru.wikipedia.org/wiki/Критерий_Поста>
<https://ru.wikipedia.org/wiki/Предполные_классы>
<https://en.wikipedia.org/wiki/Functional_completeness>
<https://www.academia.edu/12708709/Posts_functional_completeness_theorem>
<https://en.wikipedia.org/wiki/Post%27s_lattice>
Clones of closed classes, proof of equivalence of some of them: 1, `\oplus`, `\wedge`

<https://en.wikipedia.org/wiki/Sheffer_stroke>
Peirce's arrow $\downarrow$: <https://en.wikipedia.org/wiki/Logical_NOR>


<https://ru.wikipedia.org/wiki/Полином_Жегалкина>
<https://en.wikipedia.org/wiki/Zhegalkin_polynomial>
Proof of uniqueness and existence of Zhegalkin polynomial, not from wikipedia, it's cheating.
Method of computation.
`не` не может быть выражена через набор `или`, `и`
There are $2^{2^n}$ functions of $n$ variables.

Monotone functions order? <https://en.wikipedia.org/wiki/Hasse_diagram>, n-dimentional cube
Класс функций называется функционально полным в слабом смысле, если добавление в и констант 0 и 1 превращает его в функционально полный класс.

композиция монотонных функций монотонна
линейный полином жегалкина

куб для проверки на монотонность функций трех переменных --- any method for more than three dimentions?
метод неопределенных коэффициентов для проверки на линейность


# Problems

HW.01.05. $A = \{ 1, 2, 4, 5, 9 \}$, $B = \{ 2, 3, 5, 6, 9 \}$, $C = \{ 4, 5, 6, 7 \}$. Express $\{4, 5, 7\}$ and $\{1, 2, 4\}$ through A, B, C.
How to prove the latter can't be expressed?

HW.01.07. Write an equation which has set of solutions equal to _intersection_ of solution sets of equations $\sin x = |\sin x|$ and $\cos x = \tan{\tan x}$.

HW.01.09.

HW.01.16. When proving set A is equal to set B, we have to prove $A \in B$ and $B \in A$.

Proof of distributivity and absorbtion law for set operations --- <https://math.stackexchange.com/questions/239464/math-proof-of-absorption-law>
double compliment law: <https://math.stackexchange.com/questions/937166/double-complement-of-a-set-proof>



<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- discrete math">
    <p>Your browser does not support iframes.</p>
</iframe>