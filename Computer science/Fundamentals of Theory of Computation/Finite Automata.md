# Finite Automata

## Introduction to Finite Automata

**Definition**: We define a *deterministic finite automaton* to be an ordered $5$-tuple;

$$
\begin{align*}
(Q,\Sigma,\delta,q_{0},F)
\end{align*}
$$

where 
- $Q$ is a finite non-empty set of states,
- $\Sigma$ is a finite alphabet of input symbols,
- $\delta$ is a $(Q\times\Sigma)\to Q$ function, we say that $\delta$ is a transition function,
- $q_{0}$ is a state in $Q$, we say that $q_{0}$ is the initial state, and 
- $F$ is a subset of $Q$, we say that $F$ is the set of accepting states.

**Definition**: We define a *non-deterministic finite automaton* to be an order $5$-tuple;

$$
\begin{align*}
(Q,\Sigma,\delta,q_{0},F)
\end{align*}
$$

where
- $Q$ is a finite, non-empty set of states,
- $\Sigma$ is a finite alphabet of input symbols,
- $\delta$ is a $(Q\times\Sigma)\to\mathcal{P}(Q)$ function, we say that $\delta$ is the state transition function,
- $q_{0}$ is a state in $Q$, we say that $q_{0}$ is the initial state of the automaton, and
- $F$ is a subset of $Q$, we say that $F$ is the set of accepting states of the automation.

**Remarks**: The difference between a deterministic and a non-deterministic automaton is the definition of the transition function. 

In a deterministic automaton, given a particular input symbol, there is exactly one state we can transition into.

In a non-deterministic automaton, there can be more than one possible states we can transition into for any particular input symbol.