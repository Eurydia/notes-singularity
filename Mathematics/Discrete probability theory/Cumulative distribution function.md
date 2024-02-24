# Cumulative distribution function

Let $(\Omega, \mathcal{F}, P)$ be a [[Discrete probability space|discrete probability space]].

The cumulative distribution function $C:\mathbb{R}\to[0,1]$ of a [[Discrete random variable|discrete random variable]] $X:\Omega\to\mathbb{R}$, evaluated at $x\in\mathbb{R}$, is the probability that $X$ will take a value less than or equal to $x$.
Symbolically, 

$$C_{X}(x) = P(X\le x)$$

Consider a random experiment of rolling a six-sided dice with $\Omega=\{1,2,3,4,5,6\}$, and a discrete random variable $V:\Omega\to\mathbb{R}$ is defined as:

$$
V(\omega) = 
\begin{cases}
6, &\omega = 6\\
5, &\omega = 5\\
4, &\omega = 4\\
3, &\omega = 3\\
2, &\omega = 2\\
1, &\omega = 1\\
\end{cases}
$$

Assuming that the dice is fair and every outcome is equally likely to occur, the probability mass function $f:\mathbb{R}\to[0,1]$ on $V$ is defined as:

$$
f_{V}(v)=\\
\begin{cases}
\frac{1}{6}, & v\in\{1,2,3,4,5,6\}\\
0, & \text{otherwise}
\end{cases}
$$

Then, the cumulative probability function $C:\mathbb{R}\to[0,1]$ on $V$, evaluated at $4$ is obtained from:

$$
\begin{align*}
C_{V}(4) &= f_{V}(1) + f_{V}(2) + f_{V}(3) + f_{V}(4)\\
&= 4\left(\frac{1}{6}\right)\\
&= \frac{2}{3}.
\end{align*}
$$

The probability that $V$ will take a value less than or equal to $4$ is $\frac{2}{3}$.