---
title:  "Logic"
layout: default

---

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

<https://ru.wikipedia.org/wiki/%D0%9A%D1%80%D0%B8%D1%82%D0%B5%D1%80%D0%B8%D0%B9_%D0%9F%D0%BE%D1%81%D1%82%D0%B0>
<https://en.wikipedia.org/wiki/Post%27s_lattice>
полином Жегалкина


<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- discrete math">
    <p>Your browser does not support iframes.</p>
</iframe>
