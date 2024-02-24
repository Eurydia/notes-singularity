# Probability measure

Let $(\Omega, \mathcal{F}, P)$ be a [[Discrete probability space|discrete probability space]].

A probability measure $P:\mathcal{F}\to[0,1]$ is a function which assigns a real number value to an [[Event|event]] in the [[Event space|event space]] $\mathcal{F}$.
Symbolically, 

$$\forall s : s\in\mathcal{F}\implies 0 \le P(s)\le1.$$

To be considered a valid probability measure, a function $f:\mathcal{F}\to\mathbb{R}$ must satisfy three requirements:

**Events has non-negative value**

The function $f$ assigns a non-negative value to each event in the event space.
Symbolically, 

$$\forall k: k\in\mathcal{F}\implies f(k)\ge 0.$$

**Measure of the sample space**

The function $f$ assigns $1$ to the entire [[Sample space|sample space]].
Symbolically,

$$\sum\limits_{\omega\in\Omega} f(\omega) = 1.$$

**Additivity for mutually exclusive events**

Two [[Mutually exclusive events|mutually exclusive]] events $a$ and $b$ in $\mathcal{F}$ (i.e. $a\cap b=\emptyset$), $f(a\cup b) = f(a) + f(b)$ holds.

