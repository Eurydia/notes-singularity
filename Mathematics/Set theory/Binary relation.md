# Binary relation

## Background

### Ordered pair

**Definition**: An ordered pair $(A, B)$ is a mathematical object, where the components $A,B$ are sets, called the **first** and **second coordinate**, respectively. Two ordered pairs $(A,B), (X,Y)$ are equal if and only if $A=X$ and $B=Y$.

Ordered pairs can be defined in different equivalent ways, as long as the definition satisfy the equality requirement. The widely-accepted definition is given by **Kazimierz Kuratowski**, which defined an ordered pair as

$$(X,Y):=\{\{X\},\{X,Y\}\}.$$

### Cartesian product

**Definition**: The cartesian product of two sets $A,B$, denoted by $A\times B$, is a set containing all order pairs $(a,b)$ where $a\in A$ and $b\in B$. It can be expressed in using set-builder notation as

$$
A\times B := \{(a,b) : a\in A\land b\in B\}
$$

Note that the cartesian product of three or more sets is possible but it is not relevant in the current context.

### Partition of a set

**Definition**: A partition of a set $\mathcal{A}$ is a set of non-empty sets $\mathcal{X}:=\{X_{1},X_{2},X_{3},\ldots\}$ such that:
- $\mathcal{X}$ does not contain an empty set,
- $\bigcup X = \mathcal {A}$, and
- $\forall X_{i},X_{j}\in\mathcal{X} : (X_{i}\ne X_{j}\implies X_{i}\cap X_{j}=\emptyset)$.

**Definition**: The sets $X_{1},X_{2},X_{3},\ldots\in\mathcal{X}$ are called **cells** of the partition $\mathcal{X}$.

## Binary relation

**Definition**: A **binary relation** $R$ from set $A$ to set $B$ is a subset of $A\times B$, denoted by $R\subseteq A\times B$.

**Definition**: A binary relation $R\subseteq A\times B$ is said to be **homogeneous** if $A=B$. In such a case, the term "$R$ is binary relation on $A$" has the same meaning as "$R$ is a binary relation from $A$ to $A$." 

**Definition**: A binary relation $R\subseteq A\times B$ is said to be **heterogenous** if $A\ne B$.

### Notations

#### Domain and codomain

**Definition**: The **domain** of a binary relation $R\subseteq A\times B$, denoted by $\text{dmn}(R)$, is a set containing the first coordinates of ordered pairs in $R$:

$$
\text{dmn}(R) := \{a\in A : \exists b : (b\in B\land (a,b)\in R)\}.
$$

**Definition**: The **codomain** of a binary relation $R\subseteq A\times B$, denoted by $\text{codmn}(R)$, is a set containing the second coordinates of ordered pairs in $R$:

$$
\text{codmn}(R) := \{b\in B : \exists a : (a\in A\land (a,b)\in R)\}.
$$

#### Inverse

**Definition**: The **inverse** of a binary relation $R\subseteq A\times B$, denoted $R^{-1}$, is defined as:

$$
R^{-1}:= \{(b,a) : (a,b)\in R\}.
$$

#### Image and preimage

**Definition**: The **image** of a set $K$ under a binary relation $R\subseteq A\times B$, denoted by $R(K)$, is defined as:

$$
R(K) := \{b\in B : \exists k : (k\in K\land (k,b)\in R)\}.
$$

**Definition**: The **preimage** of a set $K$ under a binary relation $R\subseteq A\times B$, denoted by $R^{-1}(K)$, is defined as:

$$
R^{-1}(K) := \{a\in A : \exists k : (k\in K\land (a,k)\in R)\}.
$$

#### Restriction and extension

**Definition**: A binary relation $S\subseteq A\times B$ is said to be a **restriction** of a binary relation $R\subseteq A\times B$ if:

$$S\subseteq R.$$

**Definition**: The binary relations $S\subseteq A\times B$ is said to be a **extension** of a binary relation $R\subseteq A\times B$ if:

$$R\subseteq S.$$

**Definition**: The **restriction** of a binary relation $R\subseteq A\times B$ to a set $K$, denoted by $R|_{K}$, is defined as:

$$R|_{K} :=\{(a,b)\in R : a\in K\}$$

#### Composition

**Definition**: The composition of two binary relations $S\subseteq A\times B$ and $R\subseteq X\times Y$, denoted by $R\circ S$, is defined as:

$$
R\circ S := \{(a,y) \in A\times Y : (a,k)\in S\land (k,y)\in R\}.
$$

The composition $S\circ R$ is defined as:

$$
S\circ R := \{(x, b)\in X\times B : (x,k)\in R\land (k,b)\in S\}.
$$


### Homogeneous binary relation

#### Important properties

**Definition**: A binary relation $R$ on $X$ is said to be **transitive** if:

$$
\forall a,b,c\in X : ((a,b)\in R\land (b,c)\in R\implies (a,c)\in R).
$$

**Definition**: A binary relation $R$ on $X$ is said to be **symmetric** if:

$$
\forall a,b\in X : ((a,b)\in R \implies (b,a)\in R).
$$

**Definition**: A binary relation $R$ on $X$ is said to be **anti-symmetric** if:

$$
\forall a,b,c\in X : ((a,b)\in R\land(b,a)\in R \implies a=b).
$$

**Definition**: A binary relation $R$ on $X$ is said to be **reflexive** if:

$$\forall a\in X : (a,a)\in R.$$

**Definition**: A binary relation $R$ on $X$ is said to be **irreflexive** if:

$$
\forall a\in X : (a,a)\notin R.
$$

**Definition**: A binary relation $R$ on $X$ is said to be **trichotomous** if:

$$
\begin{align*}
\forall a,b\in X: (
(x=y\land (x,y)\notin R\land (y,x)\notin R)\lor\\
(x\ne y\land (x,y)\in R\land (y,x)\notin R)\lor\\
(x\ne y\land (x,y)\notin R\land (y,x)\in R)).
\end{align*}
$$

**Definition**: A binary relation $R$ on $X$ is said to be **dichotomous** if:

$$\forall a,b\in X : ((x,y)\in R \lor (y,x)\in R).$$

### Partial ordering and strict partial ordering

**Definition**: A binary relation $R$ on $X$ is said to **partially order** $X$ if $R$ is:
- **reflexive**,
- **anti-symmetric**, and
- **transitive**.

**Definition**: A binary relation $R$ on $X$ is to be a **strict partial order** if $R$ is:
- **irreflexive**,
- **anti-symmetric**, and
- **transitive**.

### Total ordering and strict total ordering


**Definition**: A binary relation $R$ on $X$ is said to **totally order** $X$ if $R$ is:
- **reflexive**,
- **dichotomous**,
- **anti-symmetric**, and
- **transitive**.

**Definition**: A binary relation $R$ on $X$ is to be a **strict total order** if $R$ is:
- **irreflexive**,
- **dichotomous**,
- **anti-symmetric**, and
- **transitive**.

### Equivalence relation

**Definition**: A binary relation $R$ on $X$ is said to be an equivalence relation on $X$ if $R$ is:
- **reflexive**,
- **symmetric**, and
- **transitive**.

- Least, greatest, minimal and maximal element

### Equivalence class

**Definition**: The equivalence class of an element $a\in X$ induced by the equivalence relation $R$ on $X$, denoted by $[a]_{R}$, is a **partition** of $X$ defined as:

$$
[a]_{R} := \{x\in X : (a,x)\in R\}.
$$