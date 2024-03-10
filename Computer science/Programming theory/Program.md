# Program

Given an arbitrary state space $A$, called the **base state space**, the set $\overline{A}$ is defined as 

$$\overline{A} := \{b\in B_{i} : \forall i\in\mathbb{N}^{+} : A\le B_{i}\}.$$

Informally, $\overline{A}$ is a set of **states** $b\in B$ for every **state space** $B$ where $A$ is a subspace of.

The binary relation $S\subseteq A\times (\overline{A}\cup \{\text{fail}\})^{∗∗}$ is called **program** over $A$ if

1. $\mathcal{D}_{S} = A$
2. $\forall a\in A : (\forall v \in S(a) : (|v|\ge 1\land v_{1} = a))$
3. $\forall v\in \mathcal{R}(S) : (\forall i \in\mathbb{N}^{+} : i < |v| \implies v_{i}\ne\text{fail})$
4. $\forall v\in\mathcal{R}(S): (|v|\lt\infty\implies v_{|v|}\in A\cup\text{fail})$

Informally, a **program** $S$ over $A$ assigns at least one [[Singularity/Computer science/Programming theory/Background and notations|sequence]] to every state $a\in A$. For every sequence $v\in S(a)$ assigned to a state $a\in A$, $v$ must begin with $a$. The special state $\text{fail}$ can only be the last element of the sequence $v\in S(a)$. The last state of a finite program is either a state $a\in A$ or $\text{fail}$.

## Weak program function

**Definition**: The **weak program function** of a **program** $S\subseteq A\times(\overline{A}\cup\{\text{fail}\})^{**}$ on the state space $A$, denoted by $\tilde{p}(S)$, is a binary relation $\tilde{p}(S)\subseteq A\times (A\cup\{\text{fail}\})$ such that,

1. $\mathcal{D}_{\tilde{p}(S)} = \{a\in A : S(a)\cap (\overline{A}\cup\{\text{fail}\})^{*}\ne\emptyset\}$
2. $\forall a\in\mathcal{D}_{\tilde{p}(S)} : (\tilde{p}(S)(a) = \{b\in A\cup\{\text{fail}\} : \exists v\in S(a)\cap (\overline{A}\cup\{\text{fail}\})^{*} : b = v_{|v|}\})$

Informally, if a program $S$ assigns at least one finite sequence to a state $a\in A$, then the ordered pair $(a,b)$ is a member of $\tilde{p}(S)$, where $b\in A\cup\{\text{fail}\}$ denotes the last element of the finite sequence assigned to $a$ by $S$.

## Program function

**Definition**: The **program function** of a **program** $S\subseteq A\times(\overline{A}\cup\{\text{fail}\})^{**}$ on the **state space** $A$, denoted by $p(S)$, is a binary relation $p(S)\subseteq A\times A$, such that

1. $\mathcal{D}_{p(s)} = \left\{a\in A : S(a)\subseteq \left(\overline{A}\right)^{*}\right\}$
2. $\forall a\in\mathcal{D}_{p(s)} : (p(S)(a) = \{b\in A : \exists v\in S(a) : (b = v_{|v|})\})$

Informally, if a program $S$ assigns only finite and $\text{fail}$-less sequences to a state $a\in A$, then the ordered pair $(a,b)\in A\times A$ is a member of $p(S)$, where $b\in A$ denotes the last element of the finite and $\text{fail}$-less sequence assigned to $a$ by $S$.

If $S$ assigns multiple sequences to a state $a$, if at least one of those sequence is an infinite sequence, or it contains $\text{fail}$, then $a$ will no longer be included in $\mathcal{D}_{p(s)}$.

## Solution

**Definition**: Given a **program** $S\subseteq A\times(\overline{A}\cup\{\text{fail}\})^{**}$ and a **problem** $G\subseteq A\times A$ on a state space $A$, the program $S$ is said to solve the problem $G$ if 

1. $\mathcal{D}_{G}\subseteq\mathcal{D}_{p(s)}$
2. $\forall a\in A : (p(S)(a)\subseteq G(a))$

The **program** which solves a specific **problem** is not unique. And if two programs solves the same problems, they are said to be **equivalent**.

**Definition**: The program $S$ is said to **partially solve** $F$ if

1. $\forall a \in\mathcal{D}_{F}: (\tilde{p}(S)(a)\subseteq F(a))$