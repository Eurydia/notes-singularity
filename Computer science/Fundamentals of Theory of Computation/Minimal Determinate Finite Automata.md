# Minimal Determinate Finite Automata

## Introduction

**Theorem**: $\mathcal{L}_{3}$ is closed under set complement intersection, and difference.

---

**Definition**: We say that two finite automata $A,A'$ are equivalent if $L(A)=L(A')$.

---

**Definition**: Given a language $L\subseteq\Sigma^{*}$, we say that the set $L_{p}\coloneqq\{v\in\Sigma^{*}\mid pv\in L\}$ is the suffix language of $L$ with respect to the word $p\in\Sigma^{*}$. 

Consider the following language $L= \{ab, aac, bc, aabc\}$;
- $L_{a}=\{b, ac, abc\}$
- $L_{aa} = \{c, bc\}$

We have the following properties;

$$
\begin{align*}
&(L_{p})_{q} = L_{pq}\tag{1}\\
&L_{\varepsilon}=L\tag{2}\\
&\varepsilon\in L_{p}\iff  p\in L\tag{3}
\end{align*}
$$

---

**Definition**: Given a deterministic, finite automata $A=(Q,\Sigma,\delta, q_{0},F)$, we say that the set $L(A,q)=\{v\in\Sigma^{*}\mid qv\Rightarrow^{*}_{A}p, p\in F\}$ is the suffix language of $A$ with respect to the state $q$.

We have the following properties;

$$
\begin{align*}
&(L(A,q))_{w}=L(A,\delta(q,w))\text{ for $w\in\Sigma^{*}$}\tag{1}\\
&L(A,q_{0})=L(A)\tag{2}\\
&\varepsilon\in L(A,q)\iff q\in F\tag{3}
\end{align*}
$$

---

## Myhill–Nerode Theorem

**Theorem**: Given a language $L\in\Sigma^{*}$, then

$$
\begin{align*}
L\in\mathcal{L}_{3}\iff|\{L_{p}\}_{p\in\Sigma^{*}}|\lt\infty.
\end{align*}
$$

In other words, a type-three language must have a finite set of suffix languages. If a language has infinitely many suffix language, it cannot be a type-three language.