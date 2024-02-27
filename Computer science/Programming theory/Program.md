# Program

Given an arbitrary state space $A$, called the **base state space**, the set $\overline{A}$ is defined as 

$$\overline{A} := \{b\in B_{i} : \forall i\in\mathbb{N}^{+} : A\le B_{i}\}$$

B. ¯A does not contain the
state fail. The relation S ⊆ A × ( ¯A ∪ {fail})∗∗ is called program over A, if
1. DS = A
2. ∀a ∈ A: ∀α ∈ S(a) : |α| ≥ 1 and α1 = a
3. ∀α ∈ RS : (∀i ∈ N+ : i < |α| → αi 6 = f ail)
4. ∀α ∈ RS : (|α| < ∞ → α|α| ∈ A ∪ {f ail})

Informally, a program is a function which maps every state $s$ in a [[State space|state space]] $S$, to a [[Background and notations#Sequence|sequence]] of states and failure.