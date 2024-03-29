# Background and notations

## Membership

**Definition**: An element $a$ of a set $A$ is denoted by $a\in A$.

If an element $x$ is not a member of a set $A$, it is denoted by $x\notin A$.

## Empty set

**Definition**: An empty set is defined as a set which does not contain any element, denoted by $\emptyset$:

$$
\forall x : (x\notin\emptyset).
$$

## Cardinality

**Definition**: The cardinality of a set $A$, denoted $|A|$, is the number of members in $A$. 

## Subset and superset

**Definition**: A set $A$ is said to be a **subset** of set $B$, denoted by $A\subseteq B$, if every element $a\in A$ is an element in $B$:

$$
\forall A, B : (\forall a : (a\in A\land a\in B)\implies A\subseteq B).
$$

 On the other hand, $B$ is said to be a **superset** of $A$, denoted by $A\supseteq B$ by the same definition.

**Theorem**: A set is a subset of itself:

$$\forall A : (A\subseteq A).$$

**Theorem**: Subset relation is **transitive**:

$$\forall A, B, C : \left((A\subseteq B\land B\subseteq C)\implies A\subseteq C\right)$$

**Theorem**: Subset relation is **anti-symmetric**:

$$
\forall A, B : \left((A\subseteq B\land B\subseteq A)\implies A = B\right)
$$

## Proper subset and proper superset

**Definition**: A set $A$ is said to be a **proper subset** of set $B$, denoted $A\subset B$, if every element $a\in A$ is an element in $B$, but there is at least one element $b\in B$ such that $b\notin A$:

$$
\forall A, B : (\forall a : (a\in A\land a\in B) \land \exists b : (b\in B\land b\notin A)\implies A\subset B).
$$

On the other hand, $B$ is said to be a **proper superset** of $A$, denoted by $A\supset B$.

## Complement

**Definition**: The complement of a set $X\subseteq U$ is a set, which contains elements $x\in U$, such that $x\notin X$, denoted by $X'$:

$$
X' := \{x\in U :x\notin X\}).
$$

**Theorem**: The complement of the complement of a set is the set itself: 

$$
\forall A : (A'' = A).
$$

**Theorem**: The complement of the empty set is the universe: 

$$
\emptyset' = U.
$$

**Theorem**: The complement of the universe is the empty set: 

$$
U' = \emptyset.
$$

**Theorem**: The union of a set and its complement is the universe:

$$
\forall A : (A\cup A' =U).
$$

**Theorem**: Set Complement inverts Subset relation:

$$
\forall A, B : (A\subseteq B \iff B'\subseteq A').
$$

**Theorem**: De Morgan's Laws:

$$
\forall A, B : ((A\cap B)' = A'\cup B'),
$$

and

$$
\forall A, B : ((A\cup B)' = A'\cap B').
$$

## Equality

**Definition**: The sets $A,B$ are said to be **equal** if: 

$$\forall A,B : (A\subseteq B\land B\subseteq A\implies A = B)$$

## Union 

**Definition**: The union of two sets $A,B$, denoted by $A\cup B$, is a set which contains elements from both sets:

$$
A\cup B := \{x : x\in A\lor x\in B\}.
$$

**Definition**: The union of a set of sets $\mathcal{X} :=\{X_{1},X_{2},X_{3}\ldots\}$, denoted by $\bigcup\mathcal{X}$, is defined as:

$$
\bigcup\mathcal{X} := X_{1}\cup X_{2}\cup X_{3}\cup\ldots
$$

**Theorem**: The union of any set with the empty set is the set itself:

$$
\forall A : \left(A\cup\emptyset = A\right).
$$

**Theorem**: Set union is **associative**:

$$
\forall A,B,C : \left(A\cup(B\cup C)=(A\cup B)\cup C\right)
$$

**Theorem**: Set union is **commutative**:

$$
\forall A,B : \left(A\cup B=B\cup A\right).
$$

**Theorem**: Set union is **idempotent**:

$$
\forall A : \left(A\cup A=A\right).
$$

**Theorem**: The union of any set with its superset is the superset:

$$
\forall A,B : \left((A\subseteq B)\iff A\cup B = B\right).
$$


**Theorem**: Set union is **distributive** over set intersection:

$$
\forall A,B,C : \left(A\cup (B\cap C) = (A\cup B)\cap(A\cup C)\right).
$$

## Intersection

**Definition**: The intersection of two sets $A,B\subseteq U$, denoted by $A\cap B$, is a set containing elements which appear in both sets:

$$
A\cap B := \{x : x\in A\land x\in B\}
$$

**Definition**: The intersection of a set of sets $\mathcal{X} :=\{X_{1},X_{2},X_{3}\ldots\}$, denoted by $\bigcap\mathcal{X}$, is defined as:

$$
\bigcap\mathcal{X} := X_{1}\cap X_{2}\cap X_{3}\cap\ldots
$$

**Theorem**: The intersection of any set with the empty set is the empty set:

$$
\forall A : \left(A\cap\emptyset = \emptyset\right).
$$

**Theorem**: Set intersection is **associative**:

$$
\forall A,B,C : \left(A\cap(B\cap C)=(A\cap B)\cap C\right)
$$

**Theorem**: Set intersection is **commutative**:

$$
\forall A,B : \left(A\cap B=B\cap A\right).
$$

**Theorem**: Set intersection is **idempotent**:

$$
\forall A : \left(A\cap A=A\right).
$$

**Theorem**: The intersection of a set with its subset is the subset:

$$
\forall A,B : \left((A\subseteq B)\iff A\cap B = A\right).
$$

**Theorem**: Set intersection is **distributive** over set union:

$$
\forall A,B,C : \left(A\cap (B\cup C) = (A\cap B)\cup(A\cup C)\right).
$$

## Disjointed set

**Definition**: Two sets $A,B$ are said to be **disjointed** if 

$$
A\cap B=\emptyset.
$$

## Set difference

**Definition**: The difference of $A$ from $B$, denoted by $A\setminus B$, is a set containing elements $x\in A$, such that $x\notin B$:

$$
A\setminus B := \{x : x\in A\land x\notin B\}
$$

## Symmetric difference

**Definition**: The symmetric difference of two sets $A,B$, denoted by $A\Delta B$, is a set containing elements $x\in A\cup B$, such that $x\notin A\cap B$:

$$
A\Delta B = \{x : (x\in A\land x\notin B)\lor (x\in B\land x\notin A)\}.
$$

## Powerset

**Definition**: The powerset of a set $\mathcal{X}$, denoted by $\mathcal{P}(\mathcal{X})$, is a set containing every subset of $\mathcal{X}$, including $\emptyset$ and $\mathcal{X}$:

$$
\mathcal{P}(\mathcal{X}) := \{X: X\subseteq \mathcal{X}\}
$$

The cardinality of $\mathcal{P}(X)$ is always greater than $X$, regardless of whether $X$ is a **finite** or **infinite set**.