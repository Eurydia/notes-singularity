# ZFC set theory

The ZFC set theory is an axiomatic system, which was proposed to formalize set theory. Historically, ZF,  named after mathematicians **Ernst Zermelo** and **Abraham Fraenkel**, set theory consists of eight axioms. The ninth axiom, called the axiom of choice, is what the **C** stands for.

There are many equivalent formulations of the axioms of ZF set theory. Most of the axioms state the existence of particular sets defined from other sets.

## Axioms

### Axiom of extensionality

The axiom states that; two sets are equivalent if they contain the exact same element. Essentially, this axiom defines the relation $=$ between sets.

More formally, the sets $X,Y$ are said to be equivalent if 

$$
(\forall x\in X : x\in Y)\land(\forall y\in Y : y\in X)
$$

Sometimes the relation $=$ is treated as an abbreviation of the expression 

$$X\subseteq Y\land Y\subseteq X.$$

It is worth noting that; this axiom separates **sets** from **multisets**. Consider the sets $A:=\{x\}$ and $B:=\{x,x\}$. Every element of $A$ is present in $B$ and vice versa. Since the requirement for two sets to be equal is  **weak**, the multiplicity is ignored.

### Axiom of regularity

Intuitively, this axiom arises from the famous **set contain all set** paradox. It disallows a set from containing itself.

Formally, the axiom states that every non-empty set $X$ must contain an element which is disjointed from it,

$$
\forall X : X\ne\emptyset\implies (\exists x\in X : X\cap x=\emptyset)
$$

### Axiom schema of specification

Sets can be constructed from another set via the **set-builder** notation. This axiom places restrictions on the **set-builder** notation, so that it prevents the **set-contain-all-set** paradox.


Consider a set $A$ and a predicate $p$, the subset $B\subseteq A$ can be defined in terms of the underlying set $A$ and the predicate $p$

$$B:=\{a\in A : p(a)\}$$

### Axiom of pairing

The axiom states that for every pair of sets $X,Y$, there exists a set which contains both.

$$\forall X, Y(\exists Z : X\in Z\land Y\in Z)$$

### Axiom of union

The axiom states that for any system of sets $K:=\{S_{1}, S_{2},S_{3},\ldots\}$, there exists a set $A$ which contains every elements of the set $S_{n}$ in the system $K$.

$$
\forall S\in K : (\forall x\in S : x\in A)
$$

### Axiom schema of replacement

The axiom states that the image of any set under any definable mapping is also a set. It is necessary for the construction of certain infinite sets in ZF. 

### Axiom of infinity

The axiom states that there exists an element with infinitely many elements. More specifically, the set of natural numbers.

### Axiom of power set

The axiom states that for every set $X$ there exists a set $K$ which contain every subset of $X$.

$$
\forall k\subseteq X : k\in K
$$

### Axiom of choice

The axiom states that for every system of non-empty set $X:=\{X_{1}, X_{2}, X_{3},\ldots\}$, there exists a **choice function** $f$ that maps $X_{n}\in X$ to an element $x\in X_{n}$. 
