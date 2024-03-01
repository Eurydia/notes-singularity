# State space

## State

**Definition**: Let $A_{1},\ldots, A_{n}$ for $n\in\mathbb{N}^{+}$ be typevalue-sets and let $v_{1},\ldots,v_{n}$ be unique labels identifying the typevalue-sets. 

The set $\{v_{1}: a_{1},\ldots, v_{n}: a_{n}\}$ for $i\in [1..n]$ where $a_{i}\in A_{i}$, constructed from labels and sets mentioned beforehand, is called **state**.

## State space

**Definition**: The set of all $\{v_{1}: a_{1},\ldots, v_{n}: a_{n}\}$ **states** for $i\in [1..n]$ where $a_{i}\in A_{i}$, is called **state space**, denoted by $(v_{1} : A_{1},\ldots, v_{n}: A_{n})$.

The **state space** $S:=(n:\mathbb{N}, r:\mathbb{N})$ contains

$$
\begin{matrix*}
(n:\mathbb{N},r:\mathbb{N}) = &\{\\
&&\{n:1, r:1\},&\{n:1, r:2\},&\ldots\\
&&\{n:2, r:1\},&\{n:2, r:2\},&\ldots\\
&&\vdots&\vdots\\
&\}\\
\end{matrix*}
$$

In case a **state space** contains only one component, the notation $a_{1}$ can be used instead of $\{v_{1} : a_{1}\}$ to denote a **state**. 

$$
\begin{matrix*}
S:=(n:\mathbb{N}) &= \{ 1,2,\ldots\}
\end{matrix*}
$$

**Definition**: The label $v_{i}$ of the state space $S:=(v_{1} : A_{1},\ldots, v_{n}: A_{n})$ are considered $S\to A_{i}$ functions, where $v_{i}(s)\mapsto a_{i}$ for every **state** $s = \{v_{1}:a_{1},\ldots, v_{n}:a_{n}\}$ in $S$. 

The labels $n,r$ of the **state space** $S:=(n:\mathbb{N}, r:\mathbb{N})$ behave as follow:

$$
\begin{matrix*}
&n(\{n:1,r:1\})&\mapsto&1&r(\{n:1,r:1\})&\mapsto &1\\
&n(\{n:2,r:1\})&\mapsto&2&r(\{n:2,r:1\})&\mapsto &1\\
&\vdots &&&\vdots
\end{matrix*}
$$

## Subspace of a state space

Consider two **state spaces** $X = (v_{1}: A_{1},\ldots, v_{n}: A_{n})$ and $Y = (u_{1}: B_{1},\ldots, u_{n}: B_{m})$ where $m,n\in\mathbb{N}^{+}$ and $m\le n$. 

The state space $Y$ is said to be a **subspace of state space** $X$, denoted by $Y\le X$, if there exist
an injective function $\phi: [1..m]\to[1..n]$, where $\forall i\in \mathbb{N}^{+} : i\in [1..m]\implies Y_{i} = X_{\phi(i)}$.