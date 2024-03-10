# Background and notation

## Proposition

**Definition**: A **proposition** is a statement that is either true or false. 

**Definition**: A **proposition** can be denoted by a **propositional variable**, which are capital roman letters, such as $P, Q$.

## Negation

**Definition**: **Negation** on one proposition $P$, denoted by $\neg P$, is defined as:

| $P$ | $\neg P$ |
| --- | -------- |
| 0   | 1        |
| 1   | 0        |

## Conjunction

**Definition**: **Conjunction** on two propositions $P, Q$, denoted by $P\land Q$, is defined as:

| $P$ | $Q$ | $P\land Q$ |
| --- | --- | ---------- |
| 0   | 0   | 0          |
| 1   | 0   | 0          |
| 0   | 1   | 0          |
| 1   | 1   | 1          |

**Theorem**: Conjunction is **idempotent**:

$$
\forall P : (P\land P\iff P).
$$

**Theorem**: Conjunction is **associative**:

$$
\forall P,Q,R : (P\land (Q\land R)\iff (P\land Q)\land R).
$$

**Theorem**: Conjunction is **commutative**:

$$
\forall P,Q : (P\land Q\iff Q\land P).
$$

**Theorem**: Conjunction is **distributive** oved disjunction:

$$
\forall P,Q,R : (P\land (Q\lor R)\iff (P\land Q)\lor(P\land R)).
$$

**Theorem**: Law of absorption:

$$
\forall P, Q : (P\land (P\lor Q)\iff P).
$$

**Theorem**: De Morgan's laws:

$$
\forall P, Q : (\neg(P\land Q)\iff\neg P\lor \neg Q).
$$

## Inclusive Disjunction

**Definition**: **Inclusive disjunction** on two propositions $P, Q$, denoted by $P\lor Q$, is defined as:

| $P$ | $Q$ | $P\lor Q$ |
| --- | --- | --------- |
| 0   | 0   | 0         |
| 1   | 0   | 1         |
| 0   | 1   | 1         |
| 1   | 1   | 1         |

**Theorem**: Inclusive disjunction is **idempotent**:

$$
\forall P : (P\lor P\iff P).
$$

**Theorem**: Inclusive disjunction is **associative**:

$$
\forall P,Q,R : (P\lor (Q\lor R)\iff (P\lor Q)\lor R).
$$

**Theorem**: Inclusive disjunction is **commutative**:

$$
\forall P,Q : (P\lor Q\iff Q\lor P).
$$

**Theorem**: Inclusive disjunction is **distributive** oved conjunction:

$$
\forall P,Q,R : (P\lor(Q\land R)\iff (P\lor Q)\land(P\lor R)).
$$

**Theorem**: Law of absorption:

$$
\forall P, Q : (P\lor (P\land Q)\iff P).
$$

**Theorem**: De Morgan's laws:

$$
\forall P, Q : (\neg(P\lor Q)\iff\neg P\land \neg Q).
$$

## Exclusive disjunction

**Definition**: **Exclusive disjunction** on two propositions $P, Q$, denoted by $P\oplus Q$, is defined as:

| $P$ | $Q$ | $P\oplus Q$ |
| --- | --- | --------- |
| 0   | 0   | 0         |
| 1   | 0   | 1         |
| 0   | 1   | 1         |
| 1   | 1   | 0         |

## Implication

**Definition**: **Implication** on two propositions $P, Q$, denoted by $P\implies Q$, is defined as:

| $P$ | $Q$ | $P\implies Q$ |
| --- | --- | ------------- |
| 0   | 0   | 1             |
| 1   | 0   | 0             |
| 0   | 1   | 1             |
| 1   | 1   | 1             |

**Theorem**: Modus ponens:

$$
\forall P, Q : ((P\land (P\implies Q))\implies Q).
$$

## Equality

**Definition**: **Equality** on two propositions $P, Q$, denoted by $P\iff Q$, is defined as:

| $P$ | $Q$ | $P\implies Q$ |
| --- | --- | ------------- |
| 0   | 0   | 1             |
| 1   | 0   | 0             |
| 0   | 1   | 0             |
| 1   | 1   | 1             |
