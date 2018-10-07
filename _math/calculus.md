---
title:  "Multivariable calculus"
layout: default

---

# Partial derivatives and second partial derivatives

TODO: symmetry of second derivatives, example when it's not true, <https://en.wikipedia.org/wiki/Symmetry_of_second_derivatives#Requirement_of_continuity>

# Gradient

$$
\nabla f = 
\begin{pmatrix}
\frac {\partial f}{\partial x_1} \\
\vdots \\
\frac {\partial f}{\partial x_n}
\end{pmatrix}
$$

It tells you which direction to go to get the greatest rate of increase of the function.
Its magnitude is the slope of the graph in that direction.

Gradient vector is perpendicular to countour lines.

# Directional derivative

Directional derivative along $v$ is

$$\nabla_v f(x) = \lim_{h \to 0} \frac{f(x + hv) - f(x)}{h |v|}$$

It's a dot-product of gradient and the direction:

$$\nabla_v f = \nabla f \cdot v$$

More detailed explanation:

$$
\begin{align*}
\nabla_v f & = \nabla_v f(x_1, \ldots, x_n) = \\ 
& = v_1 \frac {\partial f}{\partial x_1}(x_1) + \ldots + v_1 \frac {\partial f}{\partial x_1}(x_1) = \\
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
\end{pmatrix} = \\
& = \nabla_v f(x_1, \ldots, x_n) \cdot v = \\
& = \nabla f \cdot v
\end{align*}
$$

<iframe class="autoresize nodisplay superlearn-iframe" src="{{ site.superlearn_url }}/ht/asdf2?deckname=multivariable calculus -- ">
    <p>Your browser does not support iframes.</p>
</iframe>
