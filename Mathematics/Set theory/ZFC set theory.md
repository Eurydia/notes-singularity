# ZFC set theory

The ZFC set theory is an axiomatic system, which was proposed to formalize set theory. Historically, ZF,  named after mathematicians **Ernst Zermelo** and **Abraham Fraenkel**, set theory consists of eight axioms. The ninth axiom, called the axiom of choice, is what the **C** stands for.

There are many equivalent formulations of the axioms of ZF set theory. Most of the axioms state the existence of particular sets defined from other sets.

## Axioms

**Axiom of extensionality**: Two sets $X,Y$ are equal if they contain the exact same element:

$$
(\forall x\in X : x\in Y)\land(\forall y\in Y : y\in X).
$$

Informally, set equality $=$ is treated as an abbreviation of the expression:

$$X\subseteq Y\land Y\subseteq X.$$

This axiom separates **sets** from **multisets**. Consider the sets $A:=\{x\}$ and $B:=\{x,x\}$. Every element of $A$ is present in $B$ and vice versa. Since the requirement for two sets to be equal is  **weak**, the multiplicity is ignored.

**Axiom of regularity**: A non-empty set $X$ must contain an element which is disjointed from it.:

$$
\forall X : (X\ne\emptyset\implies (\exists x : (x\in X\implies X\cap x=\emptyset))).
$$

This axiom solves the famous **set contain all set** paradox by disallowing a set from containing itself.

**Axiom schema of specification**: Sets can be constructed from another set via the **set-builder** notation. This axiom places restrictions on the **set-builder** notation, so that it prevents the **set-contain-all-set** paradox.

Consider a set $A$ and a predicate $p$, the subset $B\subseteq A$ can be defined in terms of the underlying set $A$ and the predicate $p$

$$B:=\{a\in A : p(a)\}$$

**Axiom of pairing**: For every pair of sets $X,Y$, there exists a set $Z$ which contains both $X$ and $Y$:

$$\forall X, Y(\exists Z : X\in Z\land Y\in Z).$$

**Axiom of union**: For any set of sets $\mathcal{H}$, there exists a set $K$ which contains elements that is an element in $\mathcal{H}$:

$$
\forall\mathcal{H} : (\exists K : (\forall H : (\forall h : (h\in H\land H\in\mathcal{H}\implies h\in K)))).
$$

**Axiom schema of replacement**: The image of a set under any definable mapping is also a set. This axiom  is necessary for the construction of certain infinite sets in ZF. 

**Axiom of infinity**: There a set $X$ such that $\emptyset\in X$. If a set $Y$ is an element of $X$, then $Y\cup\{Y\}$ is also an element of $X$:

$$
\exists X : (\emptyset \in X )\land \forall Y (Y\in X\implies (Y\cup\{Y\})\in X).
$$

**Axiom of power set**: For every set $\mathcal{X}$ there exists a set $Y$ which contain every subset of $\mathcal{X}$:

$$
\forall\mathcal{X} : (\exists Y : (\forall X : (X\subseteq \mathcal{X}\implies X\in Y))).
$$

**Axiom of choice**: For every set of non-empty sets $\mathcal{X}:=\{X_{1}, X_{2}, X_{3},\ldots\}$, there exists a **choice function** $f: \mathcal{X}\to\bigcup\mathcal{X}$ that maps $X_{n}\in \mathcal{X}$ to an element $x\in X_{n}$ for every $n\in\{1,2,3,\ldots\}$:

$$
\forall\mathcal{X} : (\emptyset\notin\mathcal{X}\implies\exists f : (\forall X: (X\in\mathcal{X}\implies f(X)\in X))).
$$