# Logical disjunction

Logical disjunction (symbol $\lor$) is a binary logical connective.
This interpretation of logical disjunction is called "logical inclusive disjunction".

An operand of a conjunction is called a "disjunct".

## Definition

Given two propositions $P$ and $Q$, $P\lor Q$ is true if $P$ is true or $Q$ is true.

Alternatively, logical conjunction maybe defined from other [[Logical connective]].

From [[Logical negation]] and [[Material implication]]

$$
\begin{align*}
P\lor Q\equiv(\lnot P)\implies Q
\end{align*}
$$

From [[Logical negation]] and [[Logical conjunction]] 

$$
\begin{align*}
P\lor Q\equiv\lnot((\lnot P)\land(\lnot Q))
\end{align*}
$$

## Properties

### Commutative

Given two propositions $P$ and $Q$, $P\lor Q$ is logically equivalent to $Q\lor P$.

$$
\begin{align*}
P\lor Q\equiv Q\lor P
\end{align*}
$$

### Associative

Given three propositions $P$ $Q$, and $R$, $(P\lor Q)\lor R$ is logically equivalent to $P\lor (Q\lor R)$.

$$
\begin{align*}
(P\lor Q)\lor R\equiv P\lor(Q\lor R)
\end{align*}
$$

### Distributive

Given three propositions $P$ $Q$, and $R$, logical disjunction is distributive over the following logical connectives:

[[Logical conjunction]] 

$$
\begin{align*}
P\lor(Q\land R)\equiv(P\lor Q)\land (P\lor R)
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

### Defining [[Logical disjunction]] from [[Logical negation]] and [[Logical conjunction]] 

[[Proposition]]: $P\lor Q\equiv\lnot((\lnot P)\land(\lnot Q))$

Proof:

$$
\begin{align*}
P\lor Q&\equiv\lnot((\lnot P)\land(\lnot Q))\tag{Proposition}\\
&\equiv((\lnot\lnot P)\lor(\lnot\lnot Q))\tag{De Morgan's Law}\\
&\equiv(P\lor Q)\tag{Double negation}\\

\end{align*}
$$

## References

Logical disjunction (Wikipedia), November 14th, 2023, https://en.wikipedia.org/wiki/Logical_disjunction

