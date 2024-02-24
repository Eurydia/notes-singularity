# Probability mass function

Let $(\Omega, \mathcal{F}, P)$ be a [[Discrete probability space|discrete probability space]].

The probability mass function $p:\mathbb{R}\to[0,1]$ of a [[Discrete random variable|discrete random variable]] $X: \Omega\to\mathbb{R}$ assigns real number value to the probability that $X$ will take on a particular real number value.

The probability that $X$ will take on a particular value $x\in\mathbb{R}$, denoted by $p_X(x)$, can also be represented as:

$$P(X=x)$$ 

or 

$$P(\{\omega \in \Omega | X(\omega) = x\}).$$

The probabilities associated with all values must be non-negative and sum up to $1$.
Symbolically,

$$
\sum\limits_{x} p_{X}(x) = 1
$$

and 
$$
p_{X}(x) \ge 0 
$$

for all $x\in(-\infty,\infty)$.

Consider a random experiment of rolling a six-sided dice with $\Omega=\{1,2,3,4,5,6\}$, and a discrete random variable $V:\Omega\to\mathbb{R}$ is defined as:

$$
V(\omega) = 
\begin{cases}
1, &\omega\in\{2,3,4\}\\
0, &\omega\in\{1,5,6\}\\
\end{cases}
$$

Assuming that the dice is fair and every outcome is equally likely to occur, the probability mass function $f:\mathbb{R}\to[0,1]$ on $V$ is defined as:

$$
f_{V}(v)=\\
\begin{cases}
\frac{1}{2}, &v = 1\\
\frac{1}{2}, &v = 0\\
0, &v\notin\{1,0\}\\
\end{cases}
$$

