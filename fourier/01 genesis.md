# Genesis of Fourier analysis

$$
\newcommand{\curlies}[1]{\left\lbrace #1 \right\rbrace}
\newcommand{\abs}[1]{\left\lvert #1 \right\rvert}
$$

[will revisit later]

Let $f : \R \to \R$ be any function. Then

$$
f(x) = \underbrace{\frac{f(x) + f(-x)}{2}}_{a(x)} + \underbrace{\frac{f(x) - f(-x)}{2}}_{b(x)}
$$

Investigating $a$ and $b$,

$$
a(-x) = \frac{f(-x) + f(x)}{2} = a(x) \\
b(-x) = \frac{f(-x) - f(x)}{2} = -b(x)
$$

So $a$ is even and $b$ is odd. So we can decompose any function $f: \R \to \R$ into a sum of an even and odd function.

## Exercises

### 3.

#### (a)

Supposse $\curlies{w_n}_{n=1}^\infty$ converges to both $z$ and $w$. Then for every $\epsilon > 0$, there is an $N$ so that if $n > N$, then $\abs{w_n - w} < \epsilon/2$ and $\abs{w_n - z} < \epsilon/2$, so $\abs{w_n - w} + \abs{w_n - z} < \epsilon$. Using the triangle inequality, we know

$$
\begin{align*}
\epsilon &> \abs{w_n - w} + \abs{w_n - z} \\
&= \abs{w_n - w} + \abs{z - w_n} \\
&\geq \abs{w_n - w + z - w_n} \\
&= \abs{z - w}
\end{align*}
$$

So for every $\epsilon$, we know that $\abs{z - w} < \epsilon$, so $\abs{z - w} = 0$, so $z = w$.

### 4.

$$
e^z = \sum_{n=0}^\infty \frac{z^n}{n!}
$$

Let $\displaystyle a_n = \frac{z^n}{n!}$ as shorthand

#### (a)

$$
\sum_{n=0}^\infty \frac{1}{2^n} \to 2
$$

Suppose $N \in \N$ is an integer so that $N > 2\abs{z}$. Then if $n \geq 2N$, we can see

$$
\begin{align*}
\abs{a_{n+1}} &= \frac{\abs{z}^{n+1}}{(n+1)!} \\
&= \frac{\abs{z}}{n + 1} \cdot \frac{\abs{z}^n}{n!} \\
&= \abs{a_n} \frac{\abs{z}}{n+1} \\
&\leq \abs{a_n} \frac{\abs{z}}{2N + 1} \tag{$n \geq 2N$} \\
&< \abs{a_n} \frac{\abs{z}}{2\abs{z} + 1} \tag{$N > \abs{z}$} \\
&< \frac{\abs{a_n}}{2}
\end{align*}
$$

so each term is less than half of the previous when $n > N$.

So considering the tail of the series starting from the $(2N)^\text{th}$ term, i.e.

$$
\sum_{n=2N}^\infty \frac{z^n}{n!} = \sum_{k=0}^\infty \frac{z^{2N + k}}{(2N+k)!}
$$

We can bound each term by the corresponding term of $\curlies{\frac{\abs{z}^{2N}}{(2N)!} \cdot \frac{1}{2^k}}_{k=0}^\infty$ whose sum converges, so by problem 3(c) we know that this series converges too. Since the tail of the series converges and there are only finite terms before it, we know that the full series converges.