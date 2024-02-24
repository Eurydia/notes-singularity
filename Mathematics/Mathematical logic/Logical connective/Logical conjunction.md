# Logical conjunction

Logical conjunction (symbol $\land$) is a binary logical connective.

An operand of a conjunction is called a "conjunct".

## Definition

Given two propositions $P$ and $Q$, $P\land Q$ is true if and only if both $P$ and $Q$ are true.

Alternatively, logical conjunction maybe defined from other [[Logical connective]].

From [[Logical negation]] and [[Material implication]]

$$
\begin{align*}
P\land Q&\equiv\lnot(P\implies\lnot Q)
\end{align*}
$$

From [[Logical negation]] and [[Logical disjunction]]

$$
\begin{align*}
P\land Q&\equiv\lnot(\lnot P\lor\lnot Q)
\end{align*}
$$

## Properties

### Commutative

Given two propositions $P$ and $Q$, $P\land Q$ is logically equivalent to $Q\land P$.

$$
\begin{align*}
P\land Q&\equiv Q\land P
\end{align*}
$$

### Associative

Given three propositions $P$ $Q$, and $R$, $(P\land Q)\land R$ is logically equivalent to $P\land (Q\land R)$.

$$
\begin{align*}
(P\land Q)\land R&\equiv P\land(Q\land R)
\end{align*}
$$

### Distributive

Given three propositions $P$ $Q$, and $R$, logical conjunction is distributive over the following logical connectives:

[[Logical disjunction]] 

$$
\begin{align*}
P\land(Q\lor R)\equiv(P\land Q)\lor (P\land R)
\end{align*}
$$

[[Logical non-equivalence]]

$$
\begin{align*}
P\land(Q\oplus R)\equiv(P\land Q)\oplus (P\land R)
\end{align*}
$$

[[Material non-implication]] 

$$
\begin{align*}
P\land(Q\centernot\implies R)\equiv(P\land Q)\centernot\implies(P\land R)
\end{align*}
$$

Additionally, logical conjunction is distributive over itself.

### [[Idempotent]]

Given a propositions $P$, $P\land P$ is logically equivalent to $P$ itself.

$$
\begin{align*}
P\land P\equiv P
\end{align*}
$$

## Proofs

### Defining [[Logical conjunction]] from [[Logical negation]] and [[Material implication]] 

Proposition: $P\land Q\equiv \lnot(P\implies\lnot Q)$.

We can perform a series of equivalent transformations.
If we can transform $\lnot(P\implies\lnot Q)$ into $P\land Q$, then they are equivalent.

$$
\begin{align*}
P\land Q\equiv \lnot(P\implies\lnot Q)
\end{align*}
$$