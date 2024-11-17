# Euler's Totient and RSA

## Reduced Residue System

**Definition**: Given a positive natural number $m\in\mathbb{N^{+}}$, and a set $\mathbb{Z}_{m}$ containing all residue classes of $m$, we define the set of all invertible elements of $\mathbb{Z}_{m}$ to be; 

$$
\begin{align*}
\{\overline{a}\in\mathbb{Z}_{m}\mid\gcd(a,m)=1\}.
\end{align*}
$$

We denote this set using $\mathbb{Z}_{m}^{*}$.

**Example**: Consider $m=10$, then we have $\mathbb{Z}_{10}^{*}=\{\overline{1},\overline{3},\overline{7},\overline{9}\}$ since 1, 3, 7, and 9 are coprime with 10 and are invertible.

**Remarks**: If $m$ is a prime number, we can observer that $\mathbb{Z}_{m}^{*}$ contains all except the zero element in $\mathbb{Z}_{m}$.

**Theorem**: Given a positive natural number $m\in\mathbb{N}^{+}$ and a set $\mathbb{Z}_{m}$ containing all residue classes of $m$, then;

$$
\begin{align*}
\forall{a,b\in \mathbb{Z}_{m}^{*}}:\overline{a}\cdot\overline{b}\in\mathbb{Z}_{m}^{*}\land \frac{\overline{a}}{\overline{b}}\in\mathbb{Z}_{m}^{*}.
\end{align*}
$$

**Definition**: Given a positive natural number $m\in\mathbb{N}_{\gt0}$ and a set $\mathbb{Z}_{m}$ containing residue classes of $m$, we say that a set of integers containing exactly one element from each residue class $\overline{a}\in\mathbb{Z}_{m}^{*}$ is a reduced residue system modulo $m$.

**Remarks**: Consider $m=10$, we have infinitely many reduced residue system modulo ten, for example, $\{1,3,7,9\}$ and $\{11,13,17,19\}$.