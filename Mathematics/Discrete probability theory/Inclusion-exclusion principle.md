# Inclusion-exclusion principle

Let $(\Omega, \mathcal{F}, P)$ be a [[Discrete probability space|discrete probability space]].

This principle is a counting technique which generalizes the method of obtaining the probability of [[Joint probability of events|joint events]].

The joint probability of two events $a$ and $b$ in the [[Event space|event space]] $\mathcal{F}$ is expressed as:

$$
P(a\cup b) = P(a) + P(b) - P(a\cap b).
$$

For three events $a$, $b$ and $c$, the principle is expressed as:

$$
P(a\cup b\cup c)=P(a)+P(b)+P(c)
-P(a\cap b)-P(a\cap c)-P(b\cap c)
+P(a\cap b\cap c).
$$

The generalized form for $n$ events $a_{1}, a_{2},\ldots a_{n}$ is expressed as:

$$
\begin{align*}
P(a_{1}\cup a_{2}\cup\ldots a_{n})
&=P \text{ of singletons}\\
&-P \text{ of pairs}\\
&+P \text{ of triples}\\
&-P \text{ of quadruples}\\
&\vdots\\
&(-1)^{n-1}P(a_{1}\cap a_{2}\cap\ldots\cap a_{n})
\end{align*}
$$