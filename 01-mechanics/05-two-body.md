# 5 - The Two-Body Problem

## 5.1 Setting the Scene

Here, we go into more details on the assumption made about the form of the potential

```{math}
V = V(|\mathbf{x}_1-\mathbf{x}_2|)
```

It is helpful to visualize the situation, which we do in @fig-two-body-problem-setup, where we show the objects (masses $m_1$ and $m_2$, respectively) with position vectors $\mathbf{x}_1$ and $\mathbf{x}_2$.

```{figure} /01-mechanics/img/two-body-setup.svg
:width: 40%
:label: fig-two-body-problem-setup

A simple visualization of the setup for the two-body problem. Massed $m_1$ and $m_2$ have position vector $\mathbf{x}_1$ and $\mathbf{x}_2$, respectively. The *displacement vector* $\mathbf{r}=\mathbf{x}_1-\mathbf{x}_2$ is in the direction $\hat{\mathbf{r}}$.
```

The **displacement vector** between the two bodies is given by
```{math}
:label: eq-displacement-vector
\mathbf{r} = \mathbf{x}_1 - \mathbf{x}_2 = r \hat{\mathbf{r}}
```
with $\hat{\mathbf{r}}$ indicating the direction of $\mathbf{r}$ and $r$ its magnitude.

### The Two-Body Problem in Cartesian Coordinates

It is natural to work in the $\hat{\mathbf{r}}$ direction, but how does the problem look in Cartesian coordinates? 

First, we assume that the mass $m_1$ stands still at the origin, that is $\mathbf{x}_1 = O$. Consequently we have that $\mathbf{r} = - \mathbf{x}_2$. 
Then, we can readily establish how to translate from spherical to Cartesian (see also @fig-two-body-spherical). 
```{math}
:label: eq-spherical-coordinates
\begin{align*}
x_2 &= r\cos{\phi}\sin{\theta}\\
y_2 &= r\sin{\phi}\sin{\theta}\\
z_2 &= r\cos{\theta}
\end{align*}
```

```{figure} /01-mechanics/img/two-body-spherical.svg
:width: 50%
:label: fig-two-body-spherical

The two-body setup in both Cartesian and spherical coordinate systems.
```

Of course, we also have[^fnrsquared]

$$
r = \sqrt{x_2^2+y_2^2+z_2^2}
$$

:::{warning} Notice
We used the standard spherical coordinates $(r,\theta,\phi)$ to represent a point. Notice, however, that the values $x_2$, $y_2$ and $z_2$ are not the components of the position the vector $\mathbf{r}$, since
```{math}
:enumerated: false
\mathbf{r} = -\mathbf{x}_2 = (-x_2, -y_2, -z_2)
```
:::

:::{hint} Two-Body in Cartesian
From the equations in @eq-spherical-coordinates, we see that the Two-Body in Cartesian coordinates, having fixed mass $m_1$ at the origin, is indeed a problem in spherical coordinates. Notice that
```{math}
\begin{align*}
r &= r(t) \\
\phi &= \phi(t) \\
\theta &= \theta(t)
\end{align*}
```
That is, the spherical coordinates change with time as $m_2$ moves with respect to $m_1$. We usually omit the explicit dependency from time $t$ to keep a lightweight notation.
:::

:::{note} Angle convention
We used the “physics convention” that uses $\theta$ for the **polar angle** (angle between the radial direction and the $z$-axis) and $\phi$ for **azimuth angle** (angle in the $xy$ plane).
:::

### The central potential
We now introduce our hypothesis that the potential only depends on the displacement vector $\mathbf{r}$ rather than on the two position vectors $\mathbf{x}_1$ and $\mathbf{x}_2$, separately (see @eq-displacement-vector).

```{math}
V = V(|\mathbf{r}|)
```

:::{attention} Recall
The potential function $V$ is a **scalar field**, that is, it is a function $\mathbb{R}^3 \rightarrow \mathbb{R}$. This allows us to use the *gradient operator* $\nabla$
```{math}
:enumerated: false
\nabla_\mathbf{x} V = \left( \frac{\partial V}{\partial x}, \frac{\partial V}{\partial y}, \frac{\partial V}{\partial z} \right)
```
where, of course, $\mathbf{x}=(x,y,z)$.
:::

A central potential depends only on the magnitude of the displacement vector, ($r=|\mathbf{r}|$). Consequently, its gradient points in the radial direction $\hat{\mathbf{r}}$. The resulting force on $m_2$ therefore has only a radial component, and can be written as
$$
\mathbf{F}_2 = +\frac{\partial V}{\partial r} \hat{\mathbf{r}}
$$
The same relation must also hold in Cartesian coordinate, more precisely
$$
\mathbf{F}_2 = -\nabla_{\mathbf x_2} V
$$
Our aim here is to show that, in fact, the two equations above are equivalent and that we can use the first one, which is a one dimensional problem, rather than the second one, which is in three dimensions.

:::{warning} 
We emphasize the plus sign in the first equation for $\mathbf{F}_2$, since it is not immediately obvious why there is a plus and not a minus sign. 

Recall that in our setup $\hat{\mathbf r}=-\hat{\mathbf x}_2$. The force on $m_2$ in Cartesian coordinates is 
$$
\mathbf F_2=-\nabla_{\mathbf x_2}V.
$$

By the chain rule, since $\mathbf{r}=-\mathbf{x}_2$, we have

$$
\nabla_{\mathbf x_2}V=-\nabla_{\mathbf r}V.
$$

Therefore,

$$
\mathbf F_2=+\nabla_{\mathbf r}V
=+\frac{\partial V}{\partial r}\hat{\mathbf r}.
$$

The plus sign is thus a consequence of our particular definition of the displacement vector, which points in the opposite direction to $\mathbf{x_2}$.
:::

We show the equivalence of the two systems with an example
$$
V(r) = \frac{\alpha}{r}
$$
for any constant $\alpha \neq 0$.

In Cartesian coordinates we have
$$
V(\mathbf{x}_2) = \frac{\alpha}{\sqrt{x_2^2+y_2^2+z_2^2}}
$$
The gradient becomes
$$
\nabla_{\mathbf{x}_2} V = \left(
    -\alpha\frac{x_2}{(\sqrt{x_2^2+y_2^2+z_2^2})^3},
    -\alpha\frac{y_2}{(\sqrt{x_2^2+y_2^2+z_2^2})^3},
    -\alpha\frac{z_2}{(\sqrt{x_2^2+y_2^2+z_2^2})^3}
\right)
$$
which can be written as
$$
\nabla_{\mathbf{x}_2} V = -\alpha \frac{\mathbf{x}_2}{r^3} = \alpha\frac{\mathbf{r}}{r^3} = \frac{\alpha}{r^2} \hat{\mathbf{r}}
$$
where we used the fact that $\mathbf{r}=-\mathbf{x}_2$ and that $\mathbf{r}=r\hat{\mathbf{r}}$.

We can now write
$$
\mathbf{F}_2 = -\nabla_{\mathbf{x}_2} V = -\frac{\alpha}{r^2} \hat{\mathbf{r}}
$$

Next, let's see how the potential looks like using the radial form.
$$
\frac{\partial V}{\partial r} = -\alpha \frac{1}{r^2}
$$
This is, of course, a scalar quantity, but if now use the equation above for $\mathbf{F}$ we have 
$$
\mathbf{F}_2 = \frac{\partial V}{\partial r}\hat{\mathbf{r}} = -\frac{\alpha}{r^2}\hat{\mathbf{r}}
$$

Showing that the results obtained in the two coordinate systems are the same.


[^fnrsquared]: Recall that in spherical coordinates we have
    ```{math}
    :enumerated: false
    \begin{align*}
    \|\mathbf{r}\|^2 &= r^2(\cos^2{\phi}\sin^2{\theta} + \sin^2{\phi}\sin^2{\theta} + \cos^2{\theta}) \\
    &= r^2(\sin^2{\theta}(\cos^2{\phi}+\sin^2{\phi}) + \cos^2{\theta}) \\
    &= r^2(\sin^2{\theta}+\cos^2{\theta})\\
    &= r^2
    \end{align*}
    ```


