# Chain rule of probability

Let $(\Omega, \mathcal{F}, P)$ be a [[Discrete probability space|discrete probability space]].

The theorem describes how to calculate the probability of the [[Joint probability of events|joint events]] using [[Conditional probability of events|conditional probabilities]].

For two events $a$ and $b$ in the [[Event space|event space]] $\mathcal{F}$, where $P(a)\ne0$, the theorem is expressed as:

$$
P(b\cap a) = P(b|a)\cdot P(a)
$$

For three events $a$, $b$, and $c$m where $P(a)\ne0, P(b\cap a)\ne0$, the principle is expressed as:

$$
P(c\cap (b\cap a)) = P(c|(b\cap a))\cdot P(b|a)\cdot P(a)
$$

The generalized form for $n$ events $a_{1}, a_{2},\ldots a_{n}$ is expressed as:

$$
\begin{align*}
P(a_{n}\cap a_{n-1}\cap\ldots\cap a_{1}) =& P(a_{n}|a_{n-1}\cap a_{n-2}\cap\ldots\cap a_{1})\\
&P(a_{n-1}|a_{n-2}\cap a_{n-3}\cap\ldots\cap a_{1})\\
&\vdots\\
&P(a_{2}|a_{1})\\
&P(a_{1})\\
\end{align*}
$$