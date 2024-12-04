# Chomsky's Normal Form

## Introduction

**Definition**: Given a type-two grammar $G=(N,\Sigma, P,S)$, we say that a non-terminal symbol $X\in N$ is active if there exists a word $w\in\Sigma^{*}$ such that $X\Rightarrow^{*}_{G}w$. If we cannot derive a word from $X$ in $G$, we say that the non-terminal symbol $X$ is inactive.

**Remarks**: Essentially, a non-terminal symbol is active if we can derive at least one terminal word from it. If we cannot derive a terminal word from it, we say that it inactive.

**Application**: Consider the following type-two grammar. We will construct a set of active non-terminal symbols.

$$
\begin{align*}
S &\to A | bBD\\
A &\to AC | AD\\
B &\to ε | a | SS\\
C &\to AS | abb\\
D &\to BB
\end{align*}
$$

We will call our set of active non-terminal symbols using $A$. First, we add those non-terminal symbols which derive to at least one terminal word in one step;

$$
\begin{align*}
A_{1}=\{B,C\}
\end{align*}
$$

Then we repeat this step and include those non-terminal symbols which derive to at least one terminal word in two steps. We have

$$
\begin{align*}
A_{1}&=\{B,C\}\\
A_{2}&=A_{1}\cup\{D\}=\{B,C,D\}
\end{align*}
$$

We do not include $A$ because we cannot derive a terminal word from $A$ at all since it does not stop its derivation rule.

Next, we include those non-terminal symbols which derive to a terminal word in three steps.

$$
\begin{align*}
A_{1}&=\{B,C\}\\
A_{2}&=\{B,C,D\}\\
A_{3}&=A_{2}\cup\{S\}=\{B,C,D,S\}
\end{align*}
$$

We repeat this step and include those non-terminals that derive a terminal word in four steps, but we add no new non-terminal to our set, so this is our stopping condition.

$$
\begin{align*}
A_{1}&=\{B,C\}\\
A_{2}&=\{B,C,D\}\\
A_{3}&=\{B,C,D,S\}\\
A_{4}&=A_{3}
\end{align*}
$$

Thus the set of active non-terminal symbols is $A=A_{3}=\{B,C,D,S\}$.

---

**Definition**: Given a type-two grammar $G=(N,\Sigma,P,S)$, we say that a non-terminal symbol $Y\in N$ is reachable if there are distinct words $v_{1},v_{2}\in(N\cup \Sigma)^{*}$ such that $S\Rightarrow_{G}^{*} v_{1}Yv_{2}$. Otherwise, we say that the non-terminal $Y$ is unreachable.

**Remarks**: A non-terminal is reachable if it appears in at least one word which is derivable from the starting symbol.

**Application**: Consider the following grammar;

$$
\begin{align*}
S &\to A | bBD\\
A &\to AC | AD\\
B &\to ε | a | SS\\
C &\to AS | abb\\
D &\to BB
\end{align*}
$$

We will construct a set $R$ which contains all reachable non-terminal symbols. We start with 

$$
\begin{align*}
R_{1}=\{S\}
\end{align*}
$$

We construct $R_{2}$ by including those non-terminals that we can reach from $S$ in one step. We have

$$
\begin{align*}
R_{1}&=\{S\}\\
R_{2}&=R_{1}\cup\{A,B,D\}=\{S,A,B,D\}
\end{align*}
$$

We construct $R_{3}$ which is the same as $R_{2}$, so this is our stopping condition. We have

$$
\begin{align*}
R_{1}&=\{S\}\\
R_{2}&=\{S,A,B,D\}\\
R_{3}&=R_{2}
\end{align*}
$$

Thus our set of reachable non-terminals is $R=\{S,A,B,D\}$.

---

## Reduced Grammar

**Definition**: We say that a type-two grammar is reduced if all of its non-terminal symbols are both active and reachable.

**Application**: To reduce a grammar, we simply construct a set of active non-terminal symbols and a set of reachable non-terminal symbols. We eliminate the inactive and unreachable non-terminal. In doing so, we need to eliminate all transition rules involving inactive or unreachable non-terminal.

Consider the following grammar

$$
\begin{align*}
S &\to A | bBD\\
A &\to AC | AD\\
B &\to ε | a | SS\\
C &\to AS | abb\\
D &\to BB
\end{align*}
$$

First, we construct a set of active non-terminals which is 

$$
\begin{align*}
A=\{B,C,D,S\}.
\end{align*}
$$

The non-terminal symbol $A$ is inactive, so we remove it and the rules $S\to A$, $C\to AS$. We have

$$
\begin{align*}
S &\to \cancel{A} | bBD\\
B &\to ε | a | SS\\
C &\to \cancel{AS} | abb\\
D &\to BB
\end{align*}
$$

Using this new grammar, we will construct a set of reachable non-terminal symbols which is

$$
\begin{align*}
R=\{S,B,D\}
\end{align*}
$$

We eliminate the non-terminal symbol $C$ and transition rules involving it. We have

$$
\begin{align*}
S &\to | bBD\\
B &\to ε | a | SS\\
D &\to BB
\end{align*}
$$

Thus we have the reduce equivalent grammar.

---

## Chomsky's Normal Form

**Definition**: Given a grammar $G=(N,\Sigma,P,S)$, we say that $G$ is in Chomsky's normal form if each rule in $P$ is in one of the form;
- $S\to\varepsilon$
- $A\to BC$ for $A,B,C\in N$ such that $S\to\varepsilon\in P\implies B\ne S\land C\ne S$
- $A\to a$ for $A\in N, a\in\Sigma$

---

**Theorem**: For every type-two grammar $G$, there exists an equivalent grammar $G'$ which is in Chomsky's normal form.

**Application**: We can construct $G'$ in four steps;
- eliminate rules with non-solitary terminal 
- reduce rule length
- eliminate epsilon rules
- eliminate chain rules

We consider the following grammar 

$$
\begin{align*}
S &\to AB\\
A &\to aAa | C\\
B &\to bBb | C\\
C &\to Cabc | b | ε
\end{align*}
$$

First we identify the non-solitary rules. The solitary rules are ones which is in the form 

$$
\begin{align*}
X\to x.
\end{align*}
$$

We eliminate them by introducing non-terminal symbols. For example, we eliminate the rule $A\to aAa$ with

$$
\begin{align*}
A&\to DAD\\
D&\to a
\end{align*}
$$

We do this for the rest of the non-solitary rules. We have;

$$
\begin{align*}
S &\to AB\\
A &\to DAD | C\\
B &\to EBE | C\\
C &\to CDEF | b | ε\\
D&\to a\\
E&\to b\\
F&\to c
\end{align*}
$$

It is important to note that we do not modify the other rules, only the non-solitary ones.

Next, we perform length reduction on long rules. We archive this by introducing new non-terminal symbols. We have;

$$
\begin{align*}
S &\to AB\\
A &\to DZ_{1} | C\\
B &\to EZ_{2} | C\\
C &\to CZ_{3} | b | ε\\
D&\to a\\
E&\to b\\
F&\to c\\
Z_{1}&\to AD\\
Z_{2}&\to BE\\
Z_{3}&\to DZ_{4}\\
Z_{4}&\to EF
\end{align*}
$$

To eliminate epsilon rules, we informally introduce a new set $U$. We define $U_{1}=\{X\in N\mid X\to \varepsilon\in P\}$ then we construct $U_{2}$ from $U_{1}$ and so on. In our case

$$
\begin{align*}
U_{1}&=\{C\}\\
U_{2}&=U_{1}\cup\{A,B\}=\{C,A,B\}
\end{align*}
$$

Here, we add non-terminal symbols $A,B$ to $U_{2}$ because we can derive $C$ from them in exactly one step. The construction of $U$ is complete when we no longer add new non-terminal symbol to it.

$$
\begin{align*}
U_{1}&=\{C\}\\
U_{2}&=\{C,A,B\}\\
U_{3}&=U_{2}\cup\{S\}=\{C,A,B,S\}
\end{align*}
$$

Here we do not include the non-terminal symbols we introduced, only ones from the original set.

We construct $U_{4}$ and observe that it is the same as $U_{3}$ so we stop our construction of $U$.

It is important to note that when $S\in U$ and $S$ does not appear on the right-hand side of any of the rules, we simply add $S\to\varepsilon$ in our result which is true in our case. If $S\in U$ and $S$ appears on the right-hand side of one of the rules, we need to introduce a new start symbol $S'$ along with $S'\to S$

With $U$ constructed, we will use it to eliminate the epsilon rules by applying one of the following algorithm on the rules of the form $A\to BC$;
- $B,C\in U$, introduce $A\to B$ and $A\to C$
- $B\in U, C\notin U$, introduce $A\to C$
- $B\notin U, C\in U$, introduce $A\to B$

We have


$$
\begin{align*}
S &\to AB | A | B | \varepsilon\\
A &\to DZ_{1} | C\\
B &\to EZ_{2} | C\\
C &\to CZ_{3} | b | Z_{3}\\
D&\to a\\
E&\to b\\
F&\to c\\
Z_{1}&\to AD | D\\
Z_{2}&\to BE | E\\
Z_{3}&\to DZ_{4}\\
Z_{4}&\to EF
\end{align*}
$$

In the next step, we informally introduce a new set $H(X)=\{B\in N\mid X\Rightarrow^{*} B\}$. That is

$$
\begin{align*}
H(A)&=\{A,C,Z_{3}\}\\
H(B)&=\{B,C,Z_{3}\}\\
H(C)&=\{C,Z_{3}\}\\
H(Z_{1})&=\{Z_{1},D\}\\
H(Z_{2})&=\{Z_{2},E\}\\
H(S)&=\{S,A,B,C,Z_{3}\}\\
\end{align*}
$$

All other rules are in the form $H(X)=\{X\}$.

---