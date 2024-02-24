# Zeroth-order logic

Zeroth-order logic studies propositions and relations between propositions. 

Unlike first-order logic and higher-order logic, zeroth-order logic does study [[non-logical objects]].

This branch is also known as [[propositional logic]] and [[propositional calculus]].

## Propositions


## Logical connectives

This branch of logic does not deal with non-logical objects, predicates about them, or quantifiers.

However, all the machinery of propositional logic is included in first-order logic and higher-order logics. 

### Common logical connectives

#### Negation

**Symbol:** $\neg{A}$

It is a unary logical connective.
By definition, given a proposition $P$:
- if $P$ is true, then $\neg{P}$ is false
- if $P$ is false, then $\neg{P}$ is true

```python
def negate(P: bool) -> bool:
	if P is True:
		return False
	return True
```

#### Conjunction

**Symbol:** $A\land{B}$

Given two propositions $P$ and $Q$:
- if $P$ is true and $Q$ is true, then  $P\land{Q}$ is true
- otherwise $P\land{Q}$ is false

```python
def conjunction(P: bool, Q: bool) -> bool:
	if P is True:
		if Q is True:
			return True
	return False
```

#### Disjunction

**Symbol:** $A\lor{B}$

Given two propositions $P$ and $Q$:
- if $P$ is true, then $P\lor{Q}$ is true
- if $Q$ is true, then $P\lor{Q}$ is true
- otherwise $P\lor{Q}$ is false

```python
def disjunction(P: bool, Q: bool) -> bool:
	if P is True:
		return True
	if Q is True
		return True
	return False
```

#### Material implication

**Symbol:** $A\implies{B}$

The proposition $A$ is called the antecedent, and the proposition $B$ is called the consequent.

Given two propositions $P$ and $Q$:
- if $P$ is true but $Q$ is false, then $P\implies{Q}$ is false
- otherwise $P\implies{Q}$ is true

```python
def material_implication(P: bool, Q: bool) -> bool:
	if P is True:
		if Q is False
			return False
	return True
```

#### Equivalence

**Symbol:** $A\iff{B}$

Given two propositions $P$ and $Q$:
- if $P$ and $Q$ have the same truth-value, then $P\iff{Q}$ is true
- otherwise $P\iff{Q}$ is false

```python
def equivalence(P: bool, Q: bool) -> bool:
	if P == Q:
		return True
	return False
```

#### Exclusive disjunction

**Symbol**: $A\oplus{B}$

It is also known as non-equivalence.

Given two propositions $P$ and $Q$:
- if $P$ and $Q$ have different truth-value, then $P\oplus{Q}$ is true
- otherwise $P\oplus{Q}$ is false

```python
def exclusive_disjunction(P: bool, Q: bool) -> bool:
	if not (P == Q):
		return True
	return False
```

#### Non-conjunction

**Symbol**: $A||B$, $A\uparrow{B}$

Given two propositions $P$ and $Q$:
- if $P$ is true and $Q$ is true, then $P||Q$ is false
- otherwise $P||Q$ is true

```python
def non_conjunction(P: bool, Q: bool) -> bool:
	if P is True:
		if Q is True:
			return False
	return True
```

### Properties of logical connectives

For every proposition $A$, $B$, and $C$ the following properties hold:

#### Absorption Law

There are two forms the absorption law.

##### Left absorption form

This form states that combining a proposition $A$ with a disjunction of itself and another proposition results in $A$.

```python
A or (A and B) == A
```

**Proof**

```python
all(
	((A or (A and B)) == A) 
	for A in [True, False] 
	for B in [True, False]
)
```

##### Right absorption form

This form states that combining a proposition $A$ with a conjunction of itself and another proposition results in $A$.

```python
A and (A or B) == A
```

**Proof**


```python
all(
	((A and (A or B)) == A) 
	for A in [True, False] 
	for B in [True, False]
)
```

#### Associativity

The propositions of an associative logical connective can be swapped without altering the truth-value of the original.

```python
A and (B and C) == (A and B) and C

A or (B or C) == (A or B) or C
```

#### Commutativity

The propositions of a connective may be swapped, preserving logical equivalence to the original expression.

```python
A and B == B and A

A or B == B or A
```

[[#Material implication]] does not have this property.

#### Distributivity

A logical connective distributes over another denoted.

```python

A and (B or C) == (A and B) or (A and C)


A or (B and C) == (A or B) and (A or C)
```

Idempotence:

    Explanation: Idempotence means that when the operands of an operation are the same, the result is logically equivalent to the operand itself.
    Example: In Boolean logic, A ∧ A is equivalent to A, illustrating the idempotence property.

Involutivity (for unary connectives):

    Explanation: For unary connectives, involutivity implies that applying the operation twice results in the original operand.
    Example: In classical logic, ¬(¬A) is equivalent to A, demonstrating involutivity for the negation (¬) operator.

Monotonicity:

    Explanation: Monotonicity refers to a property where a function's value increases or remains the same when its inputs increase.
    Example: In the context of logic, the OR (∨) operation is monotonic because if A1 ≤ B1 and A2 ≤ B2, then A1 ∨ A2 ≤ B1 ∨ B2.
