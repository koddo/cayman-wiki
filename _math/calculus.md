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


$(\tg x)' = \ ?$
$$(\tg x)' = \frac{1}{\cos^2 x}$$


$(\arcsin x)' = \ ?$
$$(\arcsin x)' = \frac{1}{\sqrt{1-x^2}}$$


$(\arccos x)' = \ ?$
$$(\arccos x)' = \frac{-1}{\sqrt{1-x^2}}$$


$(\arctg x)' = \ ?$
$(\arctg x)' = \frac{1}{1+x^2}$


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




$$\int x^{-1} \, dx \ = \int \frac{1}{x} \, dx \ = \ \ln |x|$$

$$\int \frac{1}{x} \, dx = \ ?$$
$$\int \frac{1}{x} \, dx \ = \ \ln |x|$$


$$\int a^x \, dx = \ ?$$
$$\int a^x \, dx \ = \ \frac{a^x}{\ln a}$$

$$\int e^x \, dx = \ ?$$
$$\int e^x \, dx \ = \ e^x$$

$$\int \sin x \; dx = \ ?$$
$$\int \sin x \; dx \ = \ - \cos x$$


$$\int \cos x \; dx = \ ?$$

$$\int \cos x \; dx \ = \&nbsp;&nbsp;\sin x$$


$$\int \frac{1}{\cos^2 x} \; dx = \ ?$$
$$\int \frac{1}{\cos^2 x} \; dx \ = \ \tg x$$


$$\int \frac{1}{\sin^2 x} \; dx = \ ?$$
$$\int \frac{1}{\sin^2 x} \; dx \ = \ - \ctg x$$


$$\int \frac{1}{a^2 + x^2} \; dx = \ ?$$
$$\int \frac{1}{a^2 + x^2} \; dx \ = \ \frac{1}{a} \; \arctg \frac{x}{a}$$

$$\int \frac{1}{a^2 - x^2} \; dx = \ ?$$
$$\int \frac{1}{a^2 - x^2} \; dx \ = \ \frac{1}{2a} \; \ln \left| \frac{a+x}{a-x} \right|$$


$$\int \frac{1}{ \sqrt{a^2-x^2} } \; dx = \ ?$$
$$\int \frac{1}{ \sqrt{a^2-x^2} } \; dx \ = \ \arcsin \frac{x}{a}$$


$$\int \frac{1}{\sqrt{x^2 + a}} \; dx = \ ?$$
$$\int \frac{1}{\sqrt{x^2 + a}} \; dx \ = \ \ln \left| x+\sqrt{x^2 + a} \right|$$

integration by parts

$$\int u\, dv = \ ?$$
$$\int u \; dv \ = \ uv \ - \ \int v \; du$$

integration by parts

$$\int\limits_a^b u \; dv = \ ?$$
$$\int\limits_a^b u \; dv \ = \ u\,v \ \bigg|_a^b \ - \ \int\limits_a^b v \; du$$


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

$$\int \sh x \; dx = \ ?$$
$$\int \sh x \; dx \ = \ \ch x$$

$$\int \ch x \; dx = \ ?$$
$$\int \ch x \; dx \ = \ \sh x$$

$$\int \frac{1}{\sh^2 x} \; dx = \ ?$$
$$\int \frac{1}{\sh^2 x} \; dx \ = \ - \mathrm{cth} x$$

$$\int \frac{1}{\ch^2 x} \; dx = \ ?$$
$$\int \frac{1}{\ch^2 x} \; dx \ = \ \mathrm{th} x$$

five special functions in calculus
$$\int \frac{1}{\ln x} \; dx$$



$$\int e^{x^2}\; dx$$



$$\int \sin x^2 \; dx$$



$$\int \frac{e^x}{x} \; dx$$



$$\int \frac{\sin x}{x} \; dx$$

$$\int \frac{1}{\sqrt{x^2 + a^2}} \; dx = \ ?$$
$$\int \frac{1}{\sqrt{x^2 + a^2}} \; dx \ = \ \ln \left| x+\sqrt{x^2 + a^2} \right|$$


$$\int \frac{1}{\sqrt{x^2 - a^2}} \; dx = \ ?$$
$$\int \frac{1}{\sqrt{x^2 - a^2}} \; dx \ = \ \ln \left| x+\sqrt{x^2 - a^2} \right|$$


# Questions

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=multivariable calculus">
    <p>Your browser does not support iframes.</p>
</iframe>
