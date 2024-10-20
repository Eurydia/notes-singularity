# Modular Arithmetic

## Residue Classes

**Definition**: Given two integers $a,b\in\mathbb{Z}$, we say that $a,b$ are *congruent modulo* if $\exists m\in\mathbb{N}_{\gt0}:m\mid a-b$. We denote that $a,b$ are congruent modulo with respect to $m$ with $a\equiv b\mod m$, and we use $a\not\equiv b\mod m$ to that $m\not\mid a-b$.

In addition, we say that $m$ is the modulus and the full statement $a\equiv b\mod m$ is congruence. 

It is important to note that "$a\equiv b\mod m$" is a statement which we expand into $m\mid a-b$. This is different from the expression "$a\mod b$" which computes to the reminder of the integer division.

**Theorem**: Given a positive integer $m\in\mathbb{N}_{\gt0}$, the congruence relation $\equiv$ is reflexive, symmetric and transitive.

This also means that the congruence relation is an equivalence relation, and it partitions $\mathbb{Z}$ into $m$ classes.

**Definition**: We refer to the equivalence classes defined by the congruence relation as *residue classes* or *congruence classes*. Generally, we use the notation $\overline{a}$ to denote the class which contains $a$ and we may also include the modulus to avoid confusion $\overline{a}_{m}$.

**Definition**: Given a modulus $m$, we define the set which contains all residue classes of $m$ to be $\mathbb{Z}_{m}:=\{\overline{0},\overline{1},\ldots,\overline{m-1}\}$.

**Definition**: Given a modulus $m$, we say that a set of integers that containing exactly one element from each residue class of $m$ is the *complete residue system of modulus $m$*.

There are infinitely many complete residue system for any modulus $m$, but we conventionally pick the set $\{0,1,\ldots,m-1\}$ to be the complete residue system.

## Modular Arithmetic

**Theorem**: Given a modulus $m\in\mathbb{N}_{\gt0}$, and $a,b\in\mathbb{Z}$, the arithmetic operations on the residue classes as follows;

- $\overline{a}+\overline{b}=\overline{a+b}$.
- $\overline{a}-\overline{b}=\overline{a-b}$.
- $\overline{a}\cdot\overline{b}=\overline{ab}$.
- $-\overline{a}=\overline{-a}$.

We also have the properties of the operations,
- $+,\cdot$ are commutative,
- $+,\cdot$ are associative,
- $\cdot$ is distributive over $+$,
- $\overline{0}$ is the additive identity,
- $\overline{1}$ is the multiplicative identity, and
- $\overline{-a}$ is the additive inverse.

## Linear Congruences

In the previous section, we discussed about the properties of the operations on residue classes, however, we did not discuss the property of division.

**Definition**: Given a modulus $m$, for $\overline{a},\overline{b}\in\mathbb{Z}_{m}$, $\frac{\overline{a}}{\overline{b}}$ is the unique residue class $\overline{x}\in\mathbb{Z}_{m}$ such that $\overline{a\cdot x}=\overline{b}$.

**Definition**: We say that the congruence of the form $ax\equiv b\mod m$, where $x$ is the only unknown variable, is a *linear congruence*.

By expanding the definition of the congruence statement, we have 

$$m\mid b-ax.$$


We can observe their relations by expanding the definition further, we have

$$\exists y\in\mathbb{Z}:my = b-ax.$$ 


Finally, if we rearrange the equation, we have 

$$my-ax=b.$$

We can observe that this is a linear Diophantine equation and we take the same approach to solve for $x$.

**Theorem**: Given a modulus $m$, the quotient $\frac{\overline{b}}{\overline{a}}$ exists if and only if $m$ and $a$ are co-primes.

**Definition**: Given a modulus $m$, we denote the *multiplicative inverse* of $\overline{a}\in\mathbb{Z}_{m}$ with $(\overline{a})^{-1}$ or $\frac{\overline{1}}{\overline{a}}$. Additionally, if $\overline{a}$ has a multiplicative inverse, we say that $\overline{a}$ is *invertible*.

**Theorem**: Given $m$, if the quotient $\frac{\overline{b}}{\overline{a}}$ exists, then $\overline{a}$ is invertible since $\frac{\overline{b}}{\overline{a}}=\overline{b}\cdot(\overline{a})^{-1}$.

**Theorem**: If $m$ is a prime number, then all residue class in $\mathbb{Z}_{m}\setminus\{\overline{0}\}$ are invertible.

Informally, if we have a prime modulus, then we can divide by any element in the residue classes, except $\overline{0}$.