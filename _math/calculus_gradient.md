---
title:  "Calculus gradient"
layout: default

---

# Partial derivatives and second partial derivatives

## Symmetry of second partial derivatives

Under certain conditions:

$${\frac {\partial }{\partial x}}\left({\frac {\partial f}{\partial y}}\right)={\frac {\partial }{\partial y}}\left({\frac {\partial f}{\partial x}}\right)$$

TODO LOW: symmetry of second derivatives, example when it's not true, <https://en.wikipedia.org/wiki/Symmetry_of_second_derivatives#Requirement_of_continuity>

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

Gradient vector is perpendicular to contour lines.

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


# TODO LOW: Divergence, curl, Laplacian, Jacobian

<https://www.khanacademy.org/math/multivariable-calculus>

# TODO: Gradient descent


# Questions

- Q: What is partial derivative? What is second partial derivative? What is symmetry of second partial derivatives? 
- Q: What is gradient? What is its direction and magnitude? What are contour lines and their relation to gradient?
- Q: What is directional derivative? Its relation to gradient?











