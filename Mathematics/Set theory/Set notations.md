# Set notations

## Membership

An element $a$, which is a **member** of a set $A$, is denoted by $a\in A$.

If an element $x$ is not a member of a set $A$, it is denoted by $x\notin A$.

## Empty set

An empty set is a set, which is defined in such a way that it does not contain any element, denoted by $\emptyset$.

## Cardinality

The cardinality of a set $A$, denoted $|S|$, is the number of members of $A$. 

Consider a set $B:= \{\text{blue}, \text{white},\text{red}\}$, then $|B|$ is three. Repeated members are not counted so $|\{\text{blue}, \text{white},\text{red},\text{red}\}|$ is also three.

## Subset and superset

A set $A$ is said to be a **subset** of set $B$, denoted by $A\subseteq B$, if every element $a\in A$ is also an element in $B$. 

$$
A\subseteq B\implies (\forall a\in A\implies a\in B)
$$

On the other hand, $B$ is said to be a **superset** of $A$, denoted by $A\supseteq B$ by the same definition.

## Proper subset and superset

A set $A$ is said to be a **proper subset** of set $B$, denoted $A\subset B$, if every element $a\in A$ is also an element in $B$, but there is at least one element $b\in B$ such that $b\notin A$.

$$
A\subset B\implies (\forall a\in A: a\in B)\land\exists b\in B : b\notin A
$$

On the other hand, $B$ is said to be a **proper superset** of $A$, denoted by $A\supset B$.


## Set complement

The complement of a set $X\subseteq U$ is a set, which contains elements $x\in U$, such that $x\notin X$, denoted by $X'$. In other words, the set $X'$ contains those elements which are not members of $X$.

$$
X\subseteq U\implies X' = \{x\in U :x\notin X\}.
$$

## Set equality

The sets $A,B\subseteq U$ are said to be **equal** if every element $a\in A$ is an element in $B$ and every element $b\in B$ is an element in $A$. In other words, two sets are equal, if they are subsets of each other.

$$A=B\implies A\subseteq B\land B\subseteq A$$

## Set union 

The union of two sets $A,B\in U$, denoted by $A\cup B$, is a set which con[]()tains element $u\in U$ such that $u$ is an element of $A$ or $u$ is an element of $B$.

$$
A\subseteq U\land B\subseteq U\implies A\cup B = \{u\in U : u\in A\lor u\in B\}
$$

## Set intersection

The intersection of two sets $A,B\subseteq U$, denoted by $A\cap B$, is a set which contains element $u\in U$ such that $u$ is an element of $A$ and $B$ at the same time.

$$
A\subseteq U\land B\subseteq U\implies A\cap B = \{u\in U : u\in A\land u\in B\}
$$

## Set difference

The difference of a set $A\subseteq U$ from a set $B\subseteq U$, denoted by $A\setminus B$, is a set which contains elements $u\in U$, such that, $u$ is an element of $A$, but not an element of $B$. In other words, the difference of $A$ from $B$ contains elements which are in $A$ but not in $B$.

$$
A\subseteq  U\land B\subseteq U\implies A\setminus B = \{u\in U : u\in A\land u\notin B\}
$$

## Symmetric difference

The symmetric difference of two sets $A,B\in U$, denoted by $A\Delta B$, is a set which contains elements $u\in U$, such that, $u$ is an element of $A\cup B$, but not $A\cap B$. In other words, the symmetric difference of two sets $A, B$ contains elements which are in $A$ or $B$, but not both at the same time.

$$
A\subseteq U\land B\subseteq U\implies A\Delta B = \{u\in U : (u\in A\land u\notin B)\lor (u\in B\land u\notin A)\}
$$

Alternative definition in terms of $\cup$ and $\setminus$:

$$
A\subseteq U\land B\subseteq U\implies A\Delta B = \{u\in U : u\in (A\setminus B)\cup (B\setminus A)\}
$$

Definition in terms of $\cup$ and $\cap$:

$$
A\subseteq U\land B\subseteq U\implies A\Delta B = \{u\in U : u\in A\cup B\land u\notin A\cap B\}
$$

## Powerset

The powerset of a set $X\subseteq U$, denoted by $\mathcal{P}(X)$ or $2^{X}$, is a set which contains every possible subset $A$ of $X$, including $\emptyset$ and $X$ itself.

$$X\subseteq  U\implies \mathcal{P}(X) = \{A\subseteq U : A\subseteq X\}$$

The cardinality of $\mathcal{P}(X)$ is always greater than $X$, regardless of whether $X$ is a **finite** or **infinite set**.