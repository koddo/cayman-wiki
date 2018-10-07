---
title:  "Multivariable calculus"
layout: default

---

# Gradient

$$
\nabla f = 
\begin{pmatrix}
\frac {\partial f}{\partial x_1} \\
\vdots \\
\frac {\partial f}{\partial x_n}
\end{pmatrix}
$$

Gradient vector is perpendicular to countour lines.

Directional derivative along $v$ is

$$\nabla_v f(x) = \lim_{h \to 0} \frac{f(x + hv) - f(x)}{h |v|}$$

$$\nabla_v f = \nabla f \cdot v$$

$$
\begin{align*}
\nabla_v f(x_1, \ldots, x_n) & = v_1 \frac {\partial f}{\partial x_1}(x_1) + \ldots + v_1 \frac {\partial f}{\partial x_1}(x_1) = \\
& =
\begin{pmatrix}
\frac {\partial f}{\partial x_1} \\
\vdots \\
\frac {\partial f}{\partial x_n}
\end{pmatrix}
\cdot
\begin{pmatrix}
v_1 \\
\vdots \\
v_n
\end{pmatrix}
& = \nabla_v f(x_1, \ldots, x_n) \cdot v = \nabla f \cdot v
$$

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=multivariable calculus -- ">
    <p>Your browser does not support iframes.</p>
</iframe>
