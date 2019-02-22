---
title:  "Calculus"
layout: default

---

* this line gets replaced with the generated table of contents
{:toc}

# TODO

The Taylor series of $f(x)$ that is infinitely differentiable in a neighborhood of $a$
$$
\begin{align*}
&f(a)+\frac {f^{(1)}(a)}{1!} (x-a)+ \frac{f^{(2)}(a)}{2!} (x-a)^2+\frac{f^{(3)}(a)}{3!}(x-a)^3+ \cdots = \\
\\
&=\sum_{n=0}^{\infty} \frac {f^{(n)}(a)}{n!} \, (x-a)^{n}
\end{align*}
$$

Maclaurin series of $e^x$
$$e^{x} = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots + \frac{x^n}{n!} + o(x^n)$$

Maclaurin series of $\sin x$
$$\sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + o(x^8)$$



$$\sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \frac{x^9}{9!} + o(x^{10})$$


Maclaurin series of $\cos x$
$$\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \frac{x^8}{8!} + o(x^9)$$



$$\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \frac{x^8}{8!} - \frac{x^{10}}{10!} + o(x^{11})$$



Maclaurin series of $\ln (1+x)$
$$\ln(1+x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \frac{x^4}{4} + o(x^4)$$

Maclaurin series of $(1+x)^m$
$$
\begin{align*}
(1+x)^m &= 1 + mx + \frac{m(m-1)}{2!} x^2 + \frac{m(m-1)(m-2)}{3!} x^3 + \cdots + \\
\\
&+ \frac{m(m-1)\cdots(m-n+1)}{n!} x^n + o(x^n)
\end{align*}
$$

$(e^x)' = \ ?$
$(e^x)' = e^x$

$(1)' = \ ?$
$(1)' = 0$


$(x^a)' = \ ?$
$(x^a)' = a\; x^{a-1}$


$(\log_a x)' = \ ?$
$(\log_a x)' = \frac{1}{x \ln a}$


$(\ln x)' = \ ?$
$(\ln x)' = \frac{1}{x}$


$(\sin x)' = \ ?$
$(\sin x)' = \cos x$


$(\cos x)' = \ ?$
$(\cos x)' = - \sin x$


$(\operatorname{tg} x)' = \ ?$
$$(\operatorname{tg} x)' = \frac{1}{\cos^2 x}$$


$(\arcsin x)' = \ ?$
$$(\arcsin x)' = \frac{1}{\sqrt{1-x^2}}$$


$(\arccos x)' = \ ?$
$$(\arccos x)' = \frac{-1}{\sqrt{1-x^2}}$$


$(\operatorname{arctg} x)' = \ ?$
$(\operatorname{arctg} x)' = \frac{1}{1+x^2}$


$(af + bg)' = \ ?$
$(af + bg)' = af' + bg'$


$(fg)' = \ ?$
$(fg)' = f 'g + fg'$


$\left(\frac{f}{g} \right)' = \ ?$
$\left(\frac{f}{g} \right)' = \frac{f'g - fg'}{g^2}$


$\left(f (g) \right)' = \ ?$
$\left(f (g) \right)' = f'(g) \cdot g'$

$$\int x^{\alpha} \, dx = \ ?$$
$$\int x^{\alpha} \, dx \ = \ \frac{x^{\alpha+1}}{\alpha+1}, \ \ \ \ \ \alpha \neq -1$$




$$\int x^{-1} \, dx \ = \int \frac{1}{x} \, dx \ = \ \ln  \vert x \vert $$

$$\int \frac{1}{x} \, dx = \ ?$$
$$\int \frac{1}{x} \, dx \ = \ \ln  \vert x \vert $$


$$\int a^x \, dx = \ ?$$
$$\int a^x \, dx \ = \ \frac{a^x}{\ln a}$$

$$\int e^x \, dx = \ ?$$
$$\int e^x \, dx \ = \ e^x$$

$$\int \sin x \; dx = \ ?$$
$$\int \sin x \; dx \ = \ - \cos x$$


$$\int \cos x \; dx = \ ?$$

$$\int \cos x \; dx \ = \ \sin x$$


$$\int \frac{1}{\cos^2 x} \; dx = \ ?$$
$$\int \frac{1}{\cos^2 x} \; dx \ = \ \operatorname{tg} x$$


$$\int \frac{1}{\sin^2 x} \; dx = \ ?$$
$$\int \frac{1}{\sin^2 x} \; dx \ = \ - \operatorname{ctg} x$$


$$\int \frac{1}{a^2 + x^2} \; dx = \ ?$$
$$\int \frac{1}{a^2 + x^2} \; dx \ = \ \frac{1}{a} \; \operatorname{arctg} \frac{x}{a}$$

$$\int \frac{1}{a^2 - x^2} \; dx = \ ?$$
$$\int \frac{1}{a^2 - x^2} \; dx \ = \ \frac{1}{2a} \; \ln \left \vert  \frac{a+x}{a-x} \right \vert $$


$$\int \frac{1}{ \sqrt{a^2-x^2} } \; dx = \ ?$$
$$\int \frac{1}{ \sqrt{a^2-x^2} } \; dx \ = \ \arcsin \frac{x}{a}$$


$$\int \frac{1}{\sqrt{x^2 + a}} \; dx = \ ?$$
$$\int \frac{1}{\sqrt{x^2 + a}} \; dx \ = \ \ln \left \vert  x+\sqrt{x^2 + a} \right \vert $$

integration by parts

$$\int u\, dv = \ ?$$
$$\int u \; dv \ = \ uv \ - \ \int v \; du$$

integration by parts

$$\int\limits_a^b u \; dv = \ ?$$
$$\int\limits_a^b u \; dv \ = \ u\,v \ \bigg \vert _a^b \ - \ \int\limits_a^b v \; du$$


integration by substitution

$$\int f(x) \; dx = F(x)$$


$$\int f\left( \varphi(x) \right) \; d \varphi(x) = \ ?$$
$$\int f\left( \varphi(x) \right) \; d \varphi(x) \ = \ F\left( \varphi(x) \right)$$

$$\int a \; f(x) \; dx = \ ?$$
$$\int a \; f(x) \; dx \ = \ a \int f(x) \; dx$$

$$\int \left[ f(x) \pm g(x) \right] \; dx = \ ?$$
$$\int \left[ f(x) \pm g(x) \right] \; dx \ = \ \int f(x) \; dx \ \pm \ \int g(x) \; dx$$

$$\int 0\; dx = \ ?$$
$$\int 0\; dx \ = \ 0 \ + \ C$$

$$\int a \; dx = \ ?$$
$$\int a \; dx \ = \ ax$$

$$\int e^{-x^2}\; dx = \ ?$$
$$\int e^{-x^2}\; dx \ = \ \text{special function} \ (x)$$

$$\int e^{x^2}\; dx = \ ?$$
$$\int e^{x^2}\; dx \ = \ \text{special function} \ (x)$$

$$\int \frac{1}{\ln x} \; dx = \ ?$$
$$\int \frac{1}{\ln x} \; dx \ = \ \text{special function} \ (x)$$

$$\int \sin x^2 \; dx = \ ?$$
$$\int \sin x^2 \; dx \ = \ \text{special function} \ (x)$$

$$\int \cos x^2 \; dx = \ ?$$
$$\int \cos x^2 \; dx \ = \ \text{special function} \ (x)$$

$$\int \frac{\sin x}{x} \; dx = \ ?$$
$$\int \frac{\sin x}{x} \; dx \ = \ \text{special function} \ (x)$$

$$\int \frac{\cos x}{x} \; dx = \ ?$$
$$\int \frac{\cos x}{x} \; dx \ = \ \text{special function} \ (x)$$

$$\int \frac{e^x}{x} \; dx = \ ?$$
$$\int \frac{e^x}{x} \; dx \ = \ \text{special function} \ (x)$$

$$\int \operatorname{sh} x \; dx = \ ?$$
$$\int \operatorname{sh} x \; dx \ = \ \operatorname{ch} x$$

$$\int \operatorname{ch} x \; dx = \ ?$$
$$\int \operatorname{ch} x \; dx \ = \ \operatorname{sh} x$$

$$\int \frac{1}{\operatorname{sh}^2 x} \; dx = \ ?$$
$$\int \frac{1}{\operatorname{sh}^2 x} \; dx \ = \ - \mathrm{cth} x$$

$$\int \frac{1}{\operatorname{ch}^2 x} \; dx = \ ?$$
$$\int \frac{1}{\operatorname{ch}^2 x} \; dx \ = \ \mathrm{th} x$$

five special functions in calculus

$$\int \frac{1}{\ln x} \; dx$$

$$\int e^{x^2}\; dx$$

$$\int \sin x^2 \; dx$$

$$\int \frac{e^x}{x} \; dx$$



$$\int \frac{\sin x}{x} \; dx$$

$$\int \frac{1}{\sqrt{x^2 + a^2}} \; dx = \ ?$$
$$\int \frac{1}{\sqrt{x^2 + a^2}} \; dx \ = \ \ln \left \vert  x+\sqrt{x^2 + a^2} \right \vert $$


$$\int \frac{1}{\sqrt{x^2 - a^2}} \; dx = \ ?$$
$$\int \frac{1}{\sqrt{x^2 - a^2}} \; dx \ = \ \ln \left \vert  x+\sqrt{x^2 - a^2} \right \vert $$

# Series convergence

<https://en.wikipedia.org/wiki/Convergence_tests>

<http://www.math.hawaii.edu/~ralph/Classes/242/SeriesConvTests.pdf>
<http://www.toomey.org/tutor/harolds_cheat_sheets/Harolds_Series_Convergence_Tests_Cheat_Sheet_2016.pdf>

<http://tutorial.math.lamar.edu/Classes/CalcII/SeriesStrategy.aspx>
<http://www.furius.ca/cqfpub/doc/series/series.pdf>
<http://www.toomey.org/tutor/harolds_cheat_sheets/Harolds_Calculus_Notes_Cheat_Sheet_2017.pdf>
<https://www.math.wvu.edu/~hjlai/Teaching/Math156_Website/Series Cheat Sheet.pdf>
<https://www.math.hmc.edu/calculus/tutorials/convergence/>

<http://infotables.ru/matematika/66-ryady/628-priznaki-skhodimosti-chislovogo-ryada-tablitsa>

<!--- sl- --->

## Summary

Nesessary condition: if $$\lim_{n \to \infty}a_n \ne 0$$ then diverges

Absolute convergence: does $$\sum_{n=0}^\infty \left \vert a_n\right \vert $$ converge?

Conditional convergence

<br/>

Ratio test: $$ \lim _{n\to \infty }\left \vert {\frac {a_{n+1}}{a_{n}}}\right \vert =r$$

Root test: $$\lim_{n\rightarrow\infty}\sqrt[n]{ \vert a_n \vert }$$

Direct comparison: $ \vert a_n \vert \le  \vert b_n \vert $

Limit comparision: $$\lim _{n\to \infty }{\frac {a_{n}}{b_{n}}}$$

Integral test: $$\int _{1}^{\infty }f(x)\,dx=\lim _{t\to \infty }\int _{1}^{t}f(x)\,dx<\infty$$

<br/>
<br/>
<br/>

Abel's test: $$\sum a_nb_n $$

Cauchy condensation test: $$\sum_{n=0}^\infty 2^n a_{2^n}$$

<br/>
<br/>
<br/>

Harmonic series: $$\sum n^p$$ converges if $p>1$, diverges if $p \le 1$ 

Geometric series: $$\sum \left( 1 + \frac{1}{q} + \frac{1}{q^2} + \frac{1}{q^3} \ldots \right) = \frac{1}{1-q}$$, when $\vert q \vert \ < 1$

Alternating series $$\sum _{n=k}^{\infty }(-1)^{n}a_{n}$$

Telescoping test: $$\sum_{{n=1}}^{\infty }{\frac{1}{n(n+1)}} = \sum_{{n=1}}^{\infty}{\frac{1}{n} - \frac{1}{n+1}}$$, summands cancel out in partial sums.

Taylor series test: is it Taylor series?



## Root test

<https://en.wikipedia.org/wiki/Root_test>

$$\lim_{n\rightarrow\infty}\sqrt[n]{ \vert a_n \vert }$$ or $$r=\limsup_{n\to \infty }{\sqrt[{n}]{ \vert a_{n} \vert }}$$

## Telescoping test

<https://en.wikipedia.org/wiki/Telescoping_series>

<https://math.stackexchange.com/questions/104918/how-to-analyze-convergence-and-sum-of-a-telescopic-series-i-cant-find-a-generi>

## Cauchy condensation test

<https://en.wikipedia.org/wiki/Cauchy_condensation_test>

## Abel's test

<https://en.wikipedia.org/wiki/Abel's_test>

# Misc

## Bernoulli's inequality

<!--- sl- --->

It approximates exponentiation of $1+x$:

$$(1+x)^n \geq 1+nx$$ for $x \geq -1$

Or this:

$$(1+x_1)(1+x_2)\cdots(1+x_n) \ge 1+x_1+x_2+\ldots+x_n$$

## More



# Sequences

<!--- sl- --->

$$\sum \left( 1 + 2 + 3 + \ldots + n \right) = \frac{(n+1)n}{2}$$

$$\sum \left( 1 + 2 + 2^2 + 2^3 + 2^4 + 2^5 + \ldots + 2^{n-1} \right) = 2^n - 1$$

$$\sum \left( 1 + 2^2 + 3^2 + 4^2 + \ldots + n^2 \right) = \frac{n(n+1)(2n+1)}{6}$$

$$\sum \left( 1 + 2^3 + 3^3 + 4^3 + \ldots + n^3 \right) = \left( \frac{(n+1)n}{2} \right)^2$$

$$\sum \left( 1 + 2^k + 3^k + 4^k + \ldots + n^k \right)$$ is a polynomial $p(k)$ of degree $k+1$



# Limits

<!--- sl- --->

Harmonic series, <https://en.wikipedia.org/wiki/Harmonic_series_(mathematics)#Divergence>:

$$1 + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \frac{1}{5} + \ldots = \infty$$

Alternating harmonic series --- special case of Taylor series of logarithm; it's conditionally convergent, not absolutely though, if rearranged the sum becomes different:

$$1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \frac{1}{5} + \ldots = \ln 2$$

<https://en.wikipedia.org/wiki/Telescoping_series>



# Questions

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- calculus -- sequences">
    <p>Your browser does not support iframes.</p>
</iframe>

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=math -- calculus -- derivatives">
    <p>Your browser does not support iframes.</p>
</iframe>


