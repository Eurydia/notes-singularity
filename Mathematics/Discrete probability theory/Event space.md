# Event space

Let $(\Omega, \mathcal{F}, P)$ be a [[Discrete probability space|discrete probability space]].

An event space, denoted by $\mathcal{F}$, is a finite set of [[Event|events]].
It is often defined as the power set of the [[Sample space|sample space]], but it can be defined a different way.

To be considered a valid event space, a set of events must satisfy three requirements:

**Contain the sample space**

The event space must contain the sample space $\Omega$.
Symbolically,

$$
\Omega\in\mathcal{F}.
$$

**Closed under complements**

For every event $s$ in $\mathcal{F}$, its complement $(\Omega \setminus s)$ is contained in $\mathcal{F}$.
Symbolically,

$$
\forall s\in\mathcal{F} : (\Omega\setminus s)\in\mathcal{F}.
$$

**Closed under countable unions**

If $s_{1}, s_{2}, \ldots$ are events in $\mathcal{F}$, then their union $s_{1} \cup s_{2} \cup \ldots \cup s_{n}$ must also be in $\mathcal{F}$ for all $n\in\mathbb{N}$.
