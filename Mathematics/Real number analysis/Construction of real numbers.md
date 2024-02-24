# Construction of real numbers

The **real number system** is a mathematical construct that provides definitions and ways to formally interact with real numbers.

There are many equivalent methods to construct a real number system. One such method is discussed here, which is [[#Axiomatic definition]].

## Axiomatic definition

One method of constructing a real number system is through **axiomatic definition**. In this method, a real number is defined as a **field**, along with a **Dedekind-complete total-ordering** binary relation. 

- [[#Field]]
- [[#Total-ordering binary relation]]
- [[#Dedekind completeness]]

### Field

A **field** is a set $S$, along with two binary operations which are defined on said set. 
Generally, the binary operations are called **addition** and **multiplication**, denoted by $+$ and $\cdot$, respectively. They are mappings $S\times S\to S$, and they must satisfy the **field axioms**.

Let elements $a,b,c\in S$, then:
- The binary operations $+$ and $\cdot$ are **associative**: $a+(b+c)=(a+b)+c$ and $a\cdot(b\cdot c)=(a\cdot b)\cdot c$
- The binary operations $+$ and $\cdot$ are **commutative**: $a+b=b+a$ and $a\cdot b=b\cdot a$
- There exist two distinct identity elements called **additive identity** and **multiplicative identity**, denoted by $0$ and $1$, respectively, in $S$ such that $0+a=a$ and $1\cdot a = a$
- There exist **additive inverses**: for every element $a\in S$, there also exist an element in $S$, denoted by $-a$, such that $a+(-a)=0$
- There exist **multiplicative inverses**: for every element $a\in S\setminus\{0\}$, there also exist an element in $S$, denoted by $a^{-1}$, such that $a\cdot(a^{-1})=1$
- The binary operator $\cdot$ is distributive over $+$: $a\cdot(b+c)=(a\cdot b)+(a+\cdot c)$

However, it is also worth noting that there multiple equivalent ways to defined a **field**. The definition mentioned provides explanation that is easy to understand.

### Total-ordering binary relation

A binary relation $R$ on some set $S$ is said to be **totally ordered** if every pair of elements $x$ and $y$ in $S$ is **comparable**. In other words, every element in a **totally-ordered** set is related to every element, including itself.

Formally, for all elements $x,y,z\in S$, the binary relation $R$ must satisfy:
- **Reflexivity** elements are related to itself: $\forall x\in S:xRx$
- **Anti-symmetry** elements cannot precede each others: $\forall x,y\in S:xRy\land yRx\implies x=y$
- **Transitivity**: $\forall x,y,z\in S: xRy\land yRz\implies xRz$
- **Dichotomous**: $\forall x,y\in S : xRy\lor yRx$

In a real number system, such a binary relation is called **less than or equal to**, denoted by $\le$.

### Dedekind-complete binary relation

So far, the requirements are satisfied by both the real number set $\mathbb{R}$ and the rational number set $\mathbb{Q}$. This requirement is needed to distinguish the two sets apart.

The separation is done by ensuring that $\mathbb{R}$ is **infinitely dense**, however, $\mathbb{Q}$ has gaps where there are **irrational numbers**.

Formally, a **total-ordering** binary relation $R$ on some set $S$ is said to be **Dedekind-complete**, if for every non-empty subset $K\subseteq S$, the least upper bound $M$ of $K$ must be in $S$.

$\mathbb{Q}$ does not satisfy this property. Consider the subset $G:=\{x\in \mathbb{Q} : x^{2}\le 2\}$ of $\mathbb{Q}$, the least upper bound of $G$ is $\sqrt{2}$, but $\sqrt{2}\notin\mathbb{Q}$. Thus $\mathbb{Q}$ is not **Dedekind-complete**.