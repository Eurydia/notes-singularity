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

## Reduction of Finite Automation

**Definition**: Given a non-deterministic finite automaton $A\coloneqq(Q,\Sigma,\delta,q_{0},F)$, we define a *configuration* of $A$ to be a word $u$ such that

$$
\begin{align*}
u\in Q\Sigma^{*}.
\end{align*}
$$

**Definition**: Given a finite automaton $\mathcal{A}\coloneqq(Q,\Sigma,\delta,q_{0},F)$ which can be deterministic or non-deterministic, and two configurations $u,v\in Q\Sigma^{*}$ of $\mathcal{A}$, we say that 

$$
\begin{align*}
\text{$\mathcal{A}$ reduces $u$ to $v$ in one step}
\end{align*}
$$

if there exists a transition rule of the form $qa\to p$ such that $p\in\delta(q,a)$ and a word $w\in\Sigma^{*}$ such that $u=qaw$ and $v=pw$ holds. We denote this property using the notation;

$$
\begin{align*}
u\Rightarrow_{A}v.
\end{align*}
$$

**Definition**: Given a finite automaton $\mathcal{A}\coloneqq(Q,\Sigma,\delta,q_{0},F)$ and two configurations of $\mathcal{A}$, we say that

$$
\begin{align*}
\text{$\mathcal{A}$ reduces $u$ to $v$}
\end{align*}
$$

if $u=v$ or there exists an positive natural number $k\in\mathbb{N}_{\gt0}$ and $k+1$ configurations $w_{0},\ldots,w_{k}$ of $\mathcal{A}$ such that $w_{0}=u$, $w_{k}=v$ and for all $i=1,2,\ldots, k$, $w_{i-1}\Rightarrow_{A}w_{i}$ holds.

## Recognized Languages of Finite Automatons

**Definition**: Given a non-deterministic, finite automaton $\mathcal{A}\coloneqq(Q,\Sigma,\delta,q_{0},F)$, we define

$$
\begin{align*}
\text{``the language $L$ which is recognized by the non-deterministic, finite automaton $\mathcal{A}$"}
\end{align*}
$$

to be

$$
\begin{align*}
L(A)\coloneqq\{u\in\Sigma^{*}\mid \exists{a\in q_{0}, p\in F} :au\Rightarrow_{\mathcal{A}}^{*} p\}.
\end{align*}
$$

## Finite Automaton and Regular Grammars

**Theorem**: Given a non-deterministic, finite automation $\mathcal{A}$, there exists a type-three grammar $G$ such that;

$$
\begin{align*}
L(\mathcal{A})=L(G).
\end{align*}
$$

**Theorem**: Given a type-three grammar $G$, there exists a non-deterministic, finite automation $\mathcal{A}$ such that;

$$
\begin{align*}
L(\mathcal{A})=L(G).
\end{align*}
$$

## Conversion of Non-deterministic, Finite Automaton to Deterministic, Finite Automaton

**Theorem**: Given a non-deterministic, finite automaton $\mathcal{A}\coloneqq(Q,\Sigma,\delta, q_{0},F)$, there exists a deterministic, finite automation $\mathcal{A'}:=(Q',\Sigma,\delta',q_{0}',F')$ such that;

$$
\begin{align*}
L(\mathcal{A})=L(\mathcal{A'}).
\end{align*}
$$
