---
title:  "Linear algebra -- bilinear and quadratic forms"
layout: default

---

* this line gets replaced with the generated table of contents
{:toc}

# Bilinear and quadratic forms

[Degenerate bilinear form](https://en.wikipedia.org/wiki/Degenerate_bilinear_form) has a non-trivial kernel: there exist some non-zero x in V such that $B(x,y)=0$ for all $y\in V$, it's orthogonal to V.
Bilinear form is degenerate if and only if the determinant of the associated matrix is zero.

A nondegenerate (or nonsingular) form — $f(x,y)=0$ for all $y \in V$ implies that $x = 0$.

--------------------

Find kernel of bilinear form with matrix $B$.

$\operatorname{Ker} \beta(x, y) = { y \vert \forall x \beta(x, y) = 0 }$
So we have $x^t B y = 0$ for all x. We can't just get rid of $x^t$.
But we can choose $x = By$, then we have $(By)^t By = 0$, which is dot product, this means $By=0$.

--------------------

# superlearn

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- linear algebra -- bilinear and quadratic forms">
    <p>Your browser does not support iframes.</p>
</iframe>
