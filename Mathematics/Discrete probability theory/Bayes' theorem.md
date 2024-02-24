
# Bayes' theorem

Let $(\Omega, \mathcal{F}, P)$ be a [[Discrete probability space|discrete probability space]].

For two events $a$ and $b$ in the [[Event space|event space]] $\mathcal{F}$ where $P(a|b)$ is known, then

$$
P(b|a) = \frac{P(a|b)\cdot P(b)} {P(a)}
$$

holds.

It is possible to derive this theorem from the definition of [[Conditional probability of events|conditional probability]].

For two events $a$ and $b$ in the [[Event space|event space]], and $P(B)\ne0$

$$
P(a|b)= \frac{P(a\cap b)\cdot P(a)}{P(b)} \tag{definition}
$$

Since $P(a\cap b)= P(b\cap a)= P(b|a)P(a)$, substitute $P(a\cap b)$ with $P(b|a)P(a)$ 

$$
P(b|a) = \frac{P(a|b)P(b)}{P(a)}\tag{theorem}
$$