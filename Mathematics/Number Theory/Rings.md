# Rings

## Introduction

**Definition**: Given a set $R$, and two binary operators $+$ and  $\cdot$, we say that the tuple $(R,+,\cdot)$ is a *ring* if it satisfies the following axioms;

- on $+$:
	- Closure: $\forall a,b\in R : a+b\in R$
	- Associativity: $\forall a,b,c\in R : (a+b)+c=a+(b+c)$
	- Commutativity: $\forall a,b\in R : a+b=b+a$
	- Zero element: $\exists z \in R : \forall a\in R: a+ z=a$
	- Inverse: $\forall a\in R :\exists x\in R : a +x=z$
- on $\cdot$:
	- Closure: $\forall a,b\in R: a\cdot b\in R$
	- Associativity: $\forall a,b,c\in R: (a\cdot b)\cdot c=a\cdot(b\cdot c)$
- $\cdot$ is distributive over $+$: 
	- $\forall a,b,c\in R:a\cdot(b+c) =a\cdot b + a\cdot c$ 
	- $\forall a,b,c\in R:(b+c)\cdot a=b\cdot a+c\cdot a$

---

**Theorem**: Given a ring $R$, the zero element in $R$ is unique

$$
\begin{align*}
\forall a,z_{1},z_{2} \in R :a+z_{1}=a\land a+z_{2}=a\implies z_{1}=z_{2}.
\end{align*}
$$

--- 

**Theorem**: Given a ring $R$, the additive inverse element of $a\in R$ is unique

$$
\begin{align*}
\forall a,x_{1},x_{2}: a+x_{1}=z\land a+x_{2}=z\implies x_{1}=x_{2}.
\end{align*}
$$

---

**Theorem**: Given a ring $R$, the additive inverse of the zero element is itself

$$
\begin{align*}
\forall a\in R: a+z=z\implies a=z.
\end{align*}
$$

---

**Theorem**: Given a ring $R$, the zero element $z$ absorbs any element via multiplication

$$
\begin{align*}
\forall a\in R: a\cdot z=z\land z\cdot a=z.
\end{align*}
$$

---

**Definition**: For a ring $R$, we can define subtraction in terms of addition and additive inverse

$$
\begin{align*}
\forall a,b\in R: a-b\coloneqq a+(-b).
\end{align*}
$$

---

## Integral Domain

### Construction of Integral Domain

**Definition**: Given a ring $R$, we say that the ring $R$ is a commutative ring if the multiplication operation is commutative

$$
\begin{align*}
\forall a,b\in R: a\cdot b=b\cdot a.
\end{align*}
$$

---

**Definition**: Given a ring $R$, we say that an element $e\in R$ is the identity element of $R$ if

$$
\begin{align*}
\forall  a\in R: a\cdot e=a\land e\cdot a =a.
\end{align*}
$$

---

**Theorem**: Given a ring $R$, if the ring $R$ has an identity element $e\in R$, then $e$ is unique

$$
\begin{align*}
\forall a,e_{1},e_{2} :(&a\cdot e_{1}=a\land\\ 
&e_{1}\cdot a=a\land\\
&a\cdot e_{2}=a\land\\
&e_{2}\cdot a =a) \implies e_{1}=e_{2}.
\end{align*}
$$

---

**Definition**: Given a ring $R$, we say that an element $a\in R\setminus\{z\}$ is a zero divisor of in $R$ if there exists an element $b\in R\setminus\{z\}$ such that $a\cdot b=z$ or $b\cdot a=z$.

---

**Theorem**: Given residue classes of $\mathbb{Z}_{m}$, the residue class $\overline{a}\in\mathbb{Z}_{m}$ is a zero divisor in $\mathbb{Z}_{m}$ if $\overline{a}\ne\overline{0}$ and $\gcd(a,m)\ne1$.

**Remarks**: From this theorem, $\mathbb{Z}_{m}$ will have a zero divisor only when $m$ is a composite number. And $\mathbb{Z}_{p}$ where $p$ is a prime number will not have a zero divisor.

---

### Introduction of Integral Domain

**Definition**: We say that a ring $R$ is an integral domain if it satisfy the following axioms;
- $R$ has at least two elements
- $R$ is a commutative ring
- $R$ has an identity element
- $R$ does not have a zero divisor

---

## Field

### Construction of Fields

#### Multiplicative Inverse

**Definition**: Given a ring $R$ which has an identity element $e$, we say that $x\in R$ is the multiplicative inverse of $a\in R$ if 

$$
\begin{align*}
a\cdot x=e\land x\cdot a =e.
\end{align*}
$$

**Notation**: We denote $x$ with $a^{-1}$, read as "the multiplicative inverse of $a$."

---

**Definition**: Given a ring $R$, we say that an element $a\in R$ is invertible if it has a multiplicative inverse.

---

**Properties**:
- the multiplicative inverse of an element is unique
- the multiplicative inverse of the identity element is itself
- the zero element is not invertible
- A zero divisor is not invertible

### Introduction of Fields

**Definition**: We say that a ring $R$ is a field if it satisfies the following conditions;
- $R$ has at least two elements
- $R$ is a commutative ring
- $R$ has an identity element
- Every non-zero element in $R$ is invertible

**Remarks**: We can define fields in terms of a integral domain. That is, we say that a integral field $R$ is a field if every non-zero element in $R$ is invertible.

---

**Definition**: (Axiomatic definition of a field) Given a set $F$ and two binary operators $+$ and $\cdot$, we say that the tuple $(F,+,\cdot)$ is a field if it satisfy the field axiom;
- on the binary operator $+$
	- closure: $\forall a,b\in F: a+b\in F$
	- associativity: $\forall a,b,c\in F : (a+b)+c=a+(b+c)$
	- commutativity: $\forall a,b\in F :a+b=b+a$
	- zero element: $\exists z\in F:\forall a\in F: a+z=a$
	- additive inverse: $\forall a\in F:\exists x\in F :a+x=z$
- on the binary operator $\cdot$
	- closure: $\forall a,b\in F:a\cdot b\in F$
	- associativity: $\forall a,b\in F:a\cdot (b\cdot c)=(a\cdot b)\cdot c$
	- commutativity: $\forall a,b\in F: a\cdot b=b\cdot a$
	- identity element: $\exists e\in F\setminus\{z\}:\forall a\in F: e\cdot a=a$
	- multiplicative inverse: $\forall a\in F\setminus\{z\}:\exists x\in F:a\cdot x=e$
- $\cdot$ is distributive over $+$: $\forall a,b,c\in F: a\cdot (b+c) = a\cdot b+a\cdot c$

---

**Definition**: Given a field $F$, we division as $\frac{a}{b}\coloneqq ab^{-1}$ where $b^{-1}\ne z$.

---

## Polynomials over Rings

**Remarks**: We often see polynomials with number coefficients for example in $\mathbb{Z},\mathbb{R},\mathbb{C}$. We can generalize polynomials further by extending their coefficients to elements in a ring.

**Definition**: Give a ring $G$, we say that the set $G[x]$ is a set of containing all polynomials with variable $x$ whose coefficients are elements $G$. For example, $\mathbb{Z}_{4}[k]$ contains all polynomial with variable $k$ whose coefficient is in the residue classes modulo $4$.

---

### Properties of Polynomials over Rings

**Theorem**: Given a ring $K$, if $K$ is a commutative ring, then $K[x]$ is also a commutative ring.

---

**Theorem**: Given a ring $K$, if $K$ is a ring with identity element, then $K[x]$ is also a ring with identity element.

---

**Theorem**: Given a ring $K$, if $K$ has no zero divisor, then $K[x]$ also has no  zero divisor.

---

**Theorem**: Given a ring $K$, if $K$ is an integral domain, then $K[x]$ is also an integral domain.

---

**Theorem**: Given a ring $K$ and a polynomial $p\in K[x]$, the polynomial $p$ has no multiplicative inverse.