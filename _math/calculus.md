---
title:  "Calculus"
layout: default

---

* this line gets replaced with the generated table of contents
{:toc}

# TODO

The Taylor series of $f(x)$ that is infinitely differentiable in a neighborhood of $a$
[latex]<br />\begin{align*}<br />&amp;f(a)+\frac {f^{(1)}(a)}{1!} (x-a)+ \frac{f^{(2)}(a)}{2!} (x-a)^2+\frac{f^{(3)}(a)}{3!}(x-a)^3+ \cdots = \\<br />\\<br />&amp;=\sum_{n=0}^{\infty} \frac {f^{(n)}(a)}{n!} \, (x-a)^{n}<br />\end{align*}<br />[/latex]

Maclaurin series of $e^x$
$$e^{x} = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots + \frac{x^n}{n!} + o(x^n)$$

Maclaurin series of $\sin x$
$$\sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + o(x^8)$$<br /><br /><br /><br />$$\sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!} + \frac{x^9}{9!} + o(x^{10})$$<br />

Maclaurin series of $\cos x$
$$\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \frac{x^8}{8!} + o(x^9)$$<br /><br /><br /><br />$$\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \frac{x^6}{6!} + \frac{x^8}{8!} - \frac{x^{10}}{10!} + o(x^{11})$$<br /><br />

Maclaurin series of $\ln (1+x)$
$$\ln(1+x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \frac{x^4}{4} + o(x^4)$$

Maclaurin series of $(1+x)^m$
[latex]<br />\begin{align*}<br />(1+x)^m &amp;= 1 + mx + \frac{m(m-1)}{2!} x^2 + \frac{m(m-1)(m-2)}{3!} x^3 + \cdots + \\<br />\\<br />&amp;+ \frac{m(m-1)\cdots(m-n+1)}{n!} x^n + o(x^n)<br />\end{align*}[/latex]

derivative<br /><br /><br />$(e^x)' = \ ?$
$(e^x)' = e^x$

derivative<br /><br /><br />$(1)' = \ ?$
$(1)' = 0$

derivative<br /><br /><br />$(x^a)' = \ ?$
$(x^a)' = a\; x^{a-1}$

derivative<br /><br /><br />$(\log_a x)' = \ ?$
$(\log_a x)' = \frac{1}{x \ln a}$

derivative<br /><br /><br />$(\ln x)' = \ ?$
$(\ln x)' = \frac{1}{x}$

derivative<br><br><br>$(\sin x)' = \ ?$
$(\sin x)' = \cos x$

derivative<br /><br /><br />$(\cos x)' = \ ?$
$(\cos x)' = - \sin x$

derivative<br /><br /><br />$(\tg x)' = \ ?$
$$(\tg x)' = \frac{1}{\cos^2 x}$$

derivative<br /><br /><br />$(\arcsin x)' = \ ?$
$$(\arcsin x)' = \frac{1}{\sqrt{1-x^2}}$$

derivative<br /><br /><br />$(\arccos x)' = \ ?$
$$(\arccos x)' = \frac{-1}{\sqrt{1-x^2}}$$

derivative<br /><br /><br />$(\arctg x)' = \ ?$
$(\arctg x)' = \frac{1}{1+x^2}$

derivative<br /><br /><br />$(af + bg)' = \ ?$
$(af + bg)' = af' + bg'$

derivative<br /><br /><br />$(fg)' = \ ?$
$(fg)' = f 'g + fg'$

derivative<br /><br /><br />$\left(\frac{f}{g} \right)' = \ ?$
$\left(\frac{f}{g} \right)' = \frac{f'g - fg'}{g^2}$

derivative<br /><br /><br />$\left(f (g) \right)' = \ ?$
$\left(f (g) \right)' = f'(g) \cdot g'$

integration<br /><br /><br />$$\int x^{\alpha} \, dx = \ ?$$
$$\int x^{\alpha} \, dx \ = \ \frac{x^{\alpha+1}}{\alpha+1}, \ \ \ \ \ \alpha \neq -1$$<br /><br /><br /><br /><br />$$\int x^{-1} \, dx \ = \int \frac{1}{x} \, dx \ = \ \ln |x|$$

integration<br /><br /><br />$$\int \frac{1}{x} \, dx = \ ?$$
$$\int \frac{1}{x} \, dx \ = \ \ln |x|$$<br />

integration<br /><br /><br />$$\int a^x \, dx = \ ?$$
$$\int a^x \, dx \ = \ \frac{a^x}{\ln a}$$

integration<br /><br /><br />$$\int e^x \, dx = \ ?$$
$$\int e^x \, dx \ = \ e^x$$

integration<br /><br /><br />$$\int \sin x \; dx = \ ?$$
$$\int \sin x \; dx \ = \ - \cos x$$<br />

integration<br /><br /><br />$$\int \cos x \; dx = \ ?$$<br />
$$\int \cos x \; dx \ = \&nbsp;&nbsp;\sin x$$<br />

integration<br /><br /><br />$$\int \frac{1}{\cos^2 x} \; dx = \ ?$$
$$\int \frac{1}{\cos^2 x} \; dx \ = \ \tg x$$<br />

integration<br /><br /><br />$$\int \frac{1}{\sin^2 x} \; dx = \ ?$$
$$\int \frac{1}{\sin^2 x} \; dx \ = \ - \ctg x$$<br />

integration<br /><br /><br />$$\int \frac{1}{a^2 + x^2} \; dx = \ ?$$
$$\int \frac{1}{a^2 + x^2} \; dx \ = \ \frac{1}{a} \; \arctg \frac{x}{a}$$

integration<br /><br /><br />$$\int \frac{1}{a^2 - x^2} \; dx = \ ?$$
$$\int \frac{1}{a^2 - x^2} \; dx \ = \ \frac{1}{2a} \; \ln \left| \frac{a+x}{a-x} \right|$$<br />

integration<br /><br /><br />$$\int \frac{1}{ \sqrt{a^2-x^2} } \; dx = \ ?$$
$$\int \frac{1}{ \sqrt{a^2-x^2} } \; dx \ = \ \arcsin \frac{x}{a}$$<br />

integration<br /><br /><br />$$\int \frac{1}{\sqrt{x^2 + a}} \; dx = \ ?$$
$$\int \frac{1}{\sqrt{x^2 + a}} \; dx \ = \ \ln \left| x+\sqrt{x^2 + a} \right|$$

integration by parts<br /><br />$$\int u\, dv = \ ?$$
$$\int u \; dv \ = \ uv \ - \ \int v \; du$$

integration by parts<br /><br />$$\int\limits_a^b u \; dv = \ ?$$
$$\int\limits_a^b u \; dv \ = \ u\,v \ \bigg|_a^b \ - \ \int\limits_a^b v \; du$$<br />

integration by substitution<br /><br />$$\int f(x) \; dx = F(x)$$<br /><br /><br />$$\int f\left( \varphi(x) \right) \; d \varphi(x) = \ ?$$
$$\int f\left( \varphi(x) \right) \; d \varphi(x) \ = \ F\left( \varphi(x) \right)$$

integration<br /><br /><br />$$\int a \; f(x) \; dx = \ ?$$
$$\int a \; f(x) \; dx \ = \ a \int f(x) \; dx$$

integration<br /><br /><br />$$\int \left[ f(x) \pm g(x) \right] \; dx = \ ?$$
$$\int \left[ f(x) \pm g(x) \right] \; dx \ = \ \int f(x) \; dx \ \pm \ \int g(x) \; dx$$

integration<br /><br /><br />$$\int 0\; dx = \ ?$$
$$\int 0\; dx \ = \ 0 \ + \ C$$

integration<br /><br /><br />$$\int a \; dx = \ ?$$
$$\int a \; dx \ = \ ax$$

integration<br /><br /><br />$$\int e^{-x^2}\; dx = \ ?$$
$$\int e^{-x^2}\; dx \ = \ \text{special function} \ (x)$$

integration<br /><br /><br />$$\int e^{x^2}\; dx = \ ?$$
$$\int e^{x^2}\; dx \ = \ \text{special function} \ (x)$$

integration<br /><br /><br />$$\int \frac{1}{\ln x} \; dx = \ ?$$
$$\int \frac{1}{\ln x} \; dx \ = \ \text{special function} \ (x)$$

integration<br /><br /><br />$$\int \sin x^2 \; dx = \ ?$$
$$\int \sin x^2 \; dx \ = \ \text{special function} \ (x)$$

integration<br /><br /><br />$$\int \cos x^2 \; dx = \ ?$$
$$\int \cos x^2 \; dx \ = \ \text{special function} \ (x)$$

integration<br /><br /><br />$$\int \frac{\sin x}{x} \; dx = \ ?$$
$$\int \frac{\sin x}{x} \; dx \ = \ \text{special function} \ (x)$$

integration<br /><br /><br />$$\int \frac{\cos x}{x} \; dx = \ ?$$
$$\int \frac{\cos x}{x} \; dx \ = \ \text{special function} \ (x)$$

integration<br /><br /><br />$$\int \frac{e^x}{x} \; dx = \ ?$$
$$\int \frac{e^x}{x} \; dx \ = \ \text{special function} \ (x)$$

integration<br /><br /><br />$$\int \sh x \; dx = \ ?$$
$$\int \sh x \; dx \ = \ \ch x$$

integration<br /><br /><br />$$\int \ch x \; dx = \ ?$$
$$\int \ch x \; dx \ = \ \sh x$$

integration<br /><br /><br />$$\int \frac{1}{\sh^2 x} \; dx = \ ?$$
$$\int \frac{1}{\sh^2 x} \; dx \ = \ - \mathrm{cth} x$$

integration<br /><br /><br />$$\int \frac{1}{\ch^2 x} \; dx = \ ?$$
$$\int \frac{1}{\ch^2 x} \; dx \ = \ \mathrm{th} x$$

five special functions in calculus
$$\int \frac{1}{\ln x} \; dx$$<br /><br /><br /><br />$$\int e^{x^2}\; dx$$<br /><br /><br /><br />$$\int \sin x^2 \; dx$$<br /><br /><br /><br />$$\int \frac{e^x}{x} \; dx$$<br /><br /><br /><br />$$\int \frac{\sin x}{x} \; dx$$

<div>integration</div><div><br /></div><div><br /></div><div>$$\int \frac{1}{\sqrt{x^2 + a^2}} \; dx = \ ?$$</div>
$$\int \frac{1}{\sqrt{x^2 + a^2}} \; dx \ = \ \ln \left| x+\sqrt{x^2 + a^2} \right|$$

<div>integration</div><div><br /></div><div><br /></div><div>$$\int \frac{1}{\sqrt{x^2 - a^2}} \; dx = \ ?$$</div>
$$\int \frac{1}{\sqrt{x^2 - a^2}} \; dx \ = \ \ln \left| x+\sqrt{x^2 - a^2} \right|$$


# Questions

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=multivariable calculus">
    <p>Your browser does not support iframes.</p>
</iframe>
