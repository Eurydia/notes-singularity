# State space

## State

Let $A_{1},\ldots, A_{n}$ for $n\in\mathbb{N}^{+}$ be typevalue-sets and let $v_{1},\ldots,v_{n}$ be unique labels identifying the typevalue-sets. 

The set $\{v_{1}: a_{1},\ldots, v_{n}: a_{n}\}$ for $i\in [1..n]$ where $a_{i}\in A_{i}$, constructed from labels and sets mentioned beforehand, is called **state**.

## State space

The set of all possible $\{v_{1}: a_{1},\ldots, v_{n}: a_{n}\}$ **states** for $i\in [1..n]$ where $a_{i}\in A_{i}$, is called **state space**, denoted by $(v_{1} : A_{1},\ldots, v_{n}: A_{n})$.

In case a **state space** contains only one component, the notation $a_{1}$ can be used instead of $\{v_{1} : a_{1}\}$ to denote a **state**. For example, the **state space** $S:=(n:\mathbb{N}, r:\mathbb{N})$ contains the following **states** 

$$
\begin{matrix*}
&\{\\
&&\{n:1, r:1\},&\{n:1, r:2\},&\ldots\\
&&\{n:2, r:1\},&\{n:2, r:2\},&\ldots\\
&&\vdots&\vdots\\
&\}\\
\end{matrix*}
$$

The label $v_{i}$ of the state space $S:=(v_{1} : A_{1},\ldots, v_{n}: A_{n})$ are considered functions from $S$ to $A_{i}$, where $v_{i}(s)\mapsto a_{i}$ for every **state** $s = \{v_{1}:a_{1},\ldots, v_{n}:a_{n}\}$. For example, consider the **state space** $S:=(n:\mathbb{N}, r:\mathbb{N})$, the labels $n,r$ behave as follow:

$$
\begin{matrix*}
&n(\{n:1,r:1\})&\mapsto &1\\
&n(\{n:12,r:19\})&\mapsto &12\\
&r(\{n:12,r:19\})&\mapsto &19\\
\end{matrix*}
$$

## Subspace of a state space

Consider two **state spaces** $X = (v_{1}: A_{1},\ldots, v_{n}: A_{n})$ and $Y = (u_{1}: B_{1},\ldots, u_{n}: B_{m})$ where $n, m\in\mathbb{N}^{+}$ and $m\le n$. 

The state space $Y$ is said to be a **subspace of state space** $A$, denoted by $Y\le X$, if there exist
an injective function $\phi: [1, m]\to[1, n]$, where $\forall i\in \mathbb{N}^{+} : i\in [1,m]\implies B_{i} = A_{\phi(i)}$.