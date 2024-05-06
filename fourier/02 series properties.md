# Basic properties of Fourier series

$$
\newcommand{\curlies}[1]{\left\lbrace #1 \right\rbrace}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
\newcommand{\d}{\,\text{d}}
$$

## Formulation

$$
F(x) = \sum_{n=0}^\infty a_n e^{inx}
$$

Since calculating the coefficients requires integration, we will assume from here on that all functions are Riemann integrable

### Functions on the circle

Suppose $F : S^1 \to \C$. Every point in $S^1$ has some angle $\theta$ so that the point can be written as $e^{i \theta}$, and so we can write $F$ as a function of $\theta$, i.e. define
$$
f(\theta) = F(e^{i\theta})
$$
Since $\theta$ and $\theta + 2\pi$ are equivalent, this means that if we consider $f : \R \to \C$, then $f$ is periodic with period $2\pi$. We can use this transformation to conceptualize the properties of $F$:

- if $f$ is integrable on every interval of length $2\pi$ then $F$ is integrable
- if $f$ is continuous on $\R$ (i.e. $f$ is continuous on every interval of length $2\pi$) then $F$ is continuous
- if $f$ is continuously differentiable to the $n^{th}$ order then so is $F$
- etc

In the other direction, if we have a function $f : [a, b] \to \C$ where $b - a = 2\pi$ and $f(a) = f(b)$, it can be easily extended to be a periodic function on all of $\R$, and it corresponds to a function $F : S^1 \to \C$ on the circle.

### Definition

If $f : [a, b] \to \C$ is Riemann integrable and $L = b - a$, then the **$n^\text{th}$ Fourier coefficient** of $f$ is defined by
$$
\hat f(n) = \frac{1}{L} \int_a^b f(x) e^{-2\pi i n x / L} \d x \text{ for } n \in \Z
$$
and the **Fourier series** is given by
$$
\sum_{n=-\infty}^\infty \hat f(n) e^{2\pi i n x / L}
$$

we also may use $a_n$ to denote $\hat f(n)$, and denote the Fourier series of $f$ by writing
$$
f(x) \sim \sum_{n=-\infty}^\infty a_n e^{2\pi i n x / L}
$$
The **$N^\text{th}$ partial sum** of the Fourier series of $f$ for $N \geq 0$ is given by the symmetric sum
$$
S_N(f)(x) = \sum_{n=-N}^N \hat f(n) e^{2\pi i n x / L}
$$

### Formulation

We can use our definition of partial sums to formulate our general problem:

***In what sense does $S_n(f)$ converge to $f$ as $N \to \infty$?***

## Some kernels

### Dirichlet kernel

The trigonometric polynomial $D_N : [-\pi, \pi] \to \C$ is defined as
$$
D_N(x) = \sum_{n=-N}^N e^{inx}
$$
Note that this is a Fourier series with
$$
a_n = \begin{cases} 1 & \abs{n} \leq N \\ 0 &\text{otherwise} \end{cases}
$$
We can calculate a closed form for it by applying the geometric series formula to its positive and negative halves,
$$
\sum_{n=0}^N w^n \text{ and } \sum_{n=-N}^{-1} w^n =  \sum_{n=1}^N w^{-n} \text{ where } w = e^{ix}
$$
The result is
$$
D_N(x) = \frac{\sin((N + \frac{1}{2})x)}{\sin(\frac{1}{2}x)}
$$

### Poisson kernel

