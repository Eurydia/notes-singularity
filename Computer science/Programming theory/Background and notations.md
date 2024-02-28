# Background and notations

This section clarify unorthodox notations used within [[Index of programming theory|programming theory]] notes.

## Set

**Definition**: The notation $[a,b]$ represents a short hand for the set $\{x\in\mathbb{Z} : a\le x\le b\}$. If $b\lt a$, the notation represents the empty set.

**Definition**: Given a set $H$, the notation $|H|$ represents the cardinality of $H$. In other words, $|H|$ is the number of elements in $H$. The notation $|H|\lt\infty$ expresses that $H$ is a finite set.

**Definition**: A collection of commonly used special sets are:
- $\mathbb{N}$ the set of natural numbers including zero.
- $\mathbb{N}^{+}$ the set of positive natural number.
- $\mathbb{Z}$ the set of integers.
- $\mathbb{L}$ the set of logical values.

## Sequence

**Definition**: Given a set $V$, the set containing finite and infinite **sequence** of elements of $V$ is denoted by $V^{**}$. In other words, $V^{**}:=V^{*}\cup V^{\infty}$, where the set $V^{*}$ contains every finite sequence of elements of $V$, $V^{\infty}$ contains every infinite sequence of elements of $V$, and $V^{*}\cap V^\infty=\emptyset$. 

**Definition**: Given a sequence $X$, the notation $|X|$ represents the length of $X$. If $X$ is infinite sequence, then $|X|=\infty$.

Informally, a **sequence** $X$ is an ordered collection of objects which can have finite or infinitely many **elements**. Elements of a sequence is given between angle brackets,

$$
X:= <x_{1},x_{2},\ldots>
$$

## Binary relation

**Definition**: Given two non-empty sets $A,B$, the notation $A\times B$, read as "cartesian product of $A$ and $B$", represents a set of every **ordered pairs** whose **first coordinate** comes from $A$, and the **second coordinate** comes from $B$.

Informally, consider two non-empty sets $A:=\{a_{1},\ldots, a_{m}\}$ and $B:=\{b_{1},\ldots,b_{n}\}$ for $m,n\in\mathbb{N}^{+}$, then $A\times B$ is defined as:

$$
\begin{matrix*}
&\{\\
&&(a_{1},b_{1}),&\ldots,&(a_{1},b_{n}),\\
&&\vdots,&\ddots,&\vdots\\
&&(a_{m},b_{1}),&\ldots,&(a_{m},b_{n}),\\
&\}
\end{matrix*}
$$

**Definition**: Given two non-empty sets $A,B$, a binary relation from $A$ to $B$ is a subset $R\subseteq A\times B$.

**Definition**: Given two non-empty sets $A,B$, the **domain** of a binary relation $R\subseteq A\times B$ is defined as:

$$\mathcal{D}_{R} := \{a\in A : \exists b\in B : (a,b)\in R\}$$

**Definition**: Given two non-empty sets $A,B$, the **codomain** or **range** of a binary relation $R\subseteq A\times B$ is defined as:

$$\mathcal{R}_{R} := \{b\in B : \exists a\in A : (a,b)\in R\}$$

**Definition**: Given two non-empty sets $A,B$, the **image** of an element $a\in A$ determined by a binary relation $V\subseteq A\times B$ is defined as:

$$V(a) := \{b\in B : (a,b)\in V\}.$$

Informally, the **image** of an element $a\in A$ determined by a binary relation $V\subseteq A\times B$ is a set of elements in $B$ that are $V$-related to $a$.

**Definition**: Given two non-empty sets $A,B$, a binary relation $R\subseteq A\times B$ is said to be **deterministic** if it satisfy

$$\forall a\in A : |R(a)|\le 1.$$

**Definition**: Given two non-empty sets $A,B$, a deterministic binary relation $R\subseteq A\times B$ is said to be a **partial function**, denoted by $R\in A\to B$, if $\mathcal{D}_{R}\subsetneq A$.

**Definition**: Given two non-empty sets $A,B$, a deterministic binary relation $R\subseteq A\times B$ is said to be a **(total) function**, denoted by $R: A\to B$, if $\mathcal{D}_{R}=A$.