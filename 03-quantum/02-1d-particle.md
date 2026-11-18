# 2 - A Quantum Particle in One Dimension

## 2.1 The Free Particle

### 2.1.1 A Particle on a Circle
This section studies a free particle “moving on a circle”. In my understanding, this way of speaking is a slight abuse, since the alleged circle resides on the *wavefunction*, which is not representing a position.

The wavefunction for a particle on a circle of radius $R$ is (see the box below for the proof)
```{math}
:label: eq-quantized-solution
\psi(x) = e^{i\frac{n}{R}x} \quad n \in \mathbb{Z}
```
which describes, as $x$ varies a circle in the complex plane.

```{note} How to arrive at this wavefunction
:class: dropdown
:open: false
If we insist that $\psi(x)$ is a circle if radius $R$, we must also have
$$
\psi(x)=\psi(x+2\pi R)
$$
Now, we use the fact that $\psi(x)=e^{ikx}$ (since we are dealing with a free particle) giving

$$
e^{ikx} = e^{ik(x+2\pi R)} \Rightarrow e^{2\pi i k R}=1
$$

which is true when the exponent (except, of course, $i$) is an integer multiple of $2\pi$, equivalently

$$
k = \frac{n}{R} \quad n \in \mathbb{Z}
$$
```

:::{tip} Moving on a circle in $\mathbb{C}$
By the above argument, we see that saying that the particle move in a circle is to be interpreted as saying that the wavefunction of the particle describes as circle as $x$ varies in $\mathbb{R}$.
:::

:::{important} Quantized Nature of Wavefunction
Equation @eq-quantized-solution gives the first indication of the *quantized nature* of the wavefunction, which is valid only for quantized values of $k$.
:::

#### About periodicity of $\psi(x)$

The periodicity of the function 
$$
\psi(x) = \psi(x+2\pi R)
$$
should be interpreted as stating that the **configuration space** (the set of possible positions of the particle) is periodic. In other words $x=x+2\pi R$ in the sense that the two points are really the same.

Then, we can write
$$
\int_{-\infty}^{+\infty}{|\psi(x)|^2 dx} = 
\int_{0}^{2\pi R}{|\psi(x)|^2 dx} = 2\pi R
$$
where we assumed that $\psi(x)=e^{ikx}$ for real $k$. The wavefunction of the free particle is
$$
\frac{\psi(x)}{\sqrt{2\pi R}}
$$
The probability of finding the particle in the interval $[a,b]$ is 
$$
\int_{a}^{b}\left|\frac{\psi(x)}{\sqrt{2\pi R}}\right|^2 dx = \frac{b-a}{2\pi R} .
$$
In other words, the above function leads to a *uniform* probability distribution on the interval $[0,2\pi R]$.


