# Boundedness

## Motivation

Let $H\subseteq\mathbb{R}$ be a non-empty set, the **maximal element** of $H$, denoted by $\max{H}$, is an element $a\in H$, such that

$$\forall h\in H : h\le a.$$

Let a real number $b\in H$, $b$ is said to be the **minimal element** of $H$, denoted by $\min{H}$, if 

$$\forall h\in H : b\le h$$

holds.

In other words, the maximal element of a set is the element with the greatest value of that set, and the minimal element of a set is the element with the smallest value. A set can contain only one such element, or even neither.

Consider the set of natural numbers $\mathbb{N}$, its minimal element is either zero or one, depending on the definition, but it does not contain a maximal element.
Furthermore, a set $B$, defined as $\{n\in\mathbb{R}:n\in(0,1)\}$, contains neither maximal or minimal element.

So there is need for another concept. One that is a close representation to maximal and minimal elements.

## Bounds of a set

Let $H\subseteq\mathbb{R}$ be a non-empty set, and a real number $M$, such that,

$$\forall h\in H : h\le M.$$

Then, $M$ is said to be an **upper bound** of $H$ and $H$ is **bounded from above**.
Similarly, Let a real number $m$, such that,

$$\forall h\in H : m\le h.$$

Then, $m$ is a **lower bound** of $H$ and $H$ is **bounded from below**.
A set is said to be **bounded** if it is bounded from above and below.

Upper bounds and lower bounds of a set could be good substitutes for maximal and minimal elements since they permit elements which are not members of a set, however, it is course-grained.

Consider the set $B:=\{n\in\mathbb{R} : n\in(0,1)\}$, any real number $M\ge1$ is a valid upper bound, and any real number $m\le0$ is valid lower bound. 

## Supremum and infimum

Luckily, they can be made more precise and fine-grained in the following way.

Let $H\subseteq\mathbb{R}$ be a non-empty set which is **bounded from above**, and $H_{M}\subseteq\mathbb{R}$ be set defined as

$$
\{M\in\mathbb{R} : \forall h\in H : h\le M\}.
$$

In other words, $H_{M}$ contains every valid upper bounds of $H$. Since $H$ is **bounded from above**, there must exist an upper bound of $H$, and $H_{M}$ must contain at least one element. Then, $\min{H_{M}}$ is a fine-grained substitution of the maximal element of $H$. 

$\min{H_{M}}$ is the **least upper bound** of $H$ or the **supremum** of $H$, denoted by $\text{LUB}(H)$ and $\sup H$, respectively.  


Similarly, let $H_{m}$ be a set which is **bounded from below**, and it is defined as

$$
\{m\in\mathbb{R} : \forall h\in H : m\le h\}.
$$

$H_{m}$ contains at least one element, and $\max{H_{m}}$ is a fine-grained substitution of the minimal element of $H$. 

$\max{H_{m}}$ is the **greatest lower bound** of $H$ or the **infimum** of $H$, denoted by $\text{GLD}(H)$ and $\inf H$, respectively.  

An important thing to note is that; the supremum and infimum of a set may not exist.
The set $B:=\{n\in\mathbb{R} : n\in(0,1)\}$ does not contain **maximal** or **minimal element**, but it has both **supremum** and **infimum**. Unfortunately, the set of natural numbers $\mathbb{N}$ does not contain the maximal element, nor does the supremum exist since it is **unbounded from above**.

## Uniqueness

It can be proven that; if a supremum of a set exists, it is unique.

That is, let $H\subseteq\mathbb{R}$ be a non-empty set which is bounded from above. Two real numbers $M_{1}$ and $M_{2}$ are suprema of $H$.

From the definition of supremum, $M_{1}\le M_{2}$, but also $M_{2}\le M_{1}$. The relation $\le$ is trichotomous, so the only case when both $M_{1}\le M_{2}$ and $M_{2}\le M_{1}$ holds is when $M_{1}= M_{2}$.

Similarly, if the infimum of a set exists, it is unique.

## Observation

*The supremum is also the maximal element of a set.*

We can observe that if the **maximal element** of a set exists, it is also the **supremum**.

Let a set $H\subseteq\mathbb{R}$ be a non-empty set, and suppose, for the purpose of contradiction, that $K\in H$ is the **maximal element** of $H$, but $K\ne\sup H$. There must exist a real number $x$, such that $x\lt K$. However, if $x\lt K$, then $x$ cannot be the **supremum**. Thus, such a number $x$ cannot exist, and $K$ must also be the **supremum**.

This observation also holds for infimum and minimal element.