# Minimal Determinate Finite Automata

## Introduction

**Theorem**: $\mathcal{L}_{3}$ is closed under set complement intersection, and difference.

---

**Definition**: We say that two finite automata $A,A'$ are equivalent if $L(A)=L(A')$.

---

**Definition**: Given a language $L\subseteq\Sigma^{*}$, we say that the set $L_{p}\coloneqq\{v\in\Sigma^{*}\mid pv\in L\}$ is the suffix language of $L$ with respect to the word $p\in\Sigma^{*}$. 

Consider the following language $L= \{ab, aac, bc, aabc\}$;
- $L_{a}=\{b, ac, abc\}$
- $L_{aa} = \{c, bc\}$

We have the following properties;

$$
\begin{align*}
&(L_{p})_{q} = L_{pq}\tag{1}\\
&L_{\varepsilon}=L\tag{2}\\
&\varepsilon\in L_{p}\iff  p\in L\tag{3}
\end{align*}
$$

---

**Definition**: Given a deterministic, finite automata $A=(Q,\Sigma,\delta, q_{0},F)$, we say that the set $L(A,q)=\{v\in\Sigma^{*}\mid qv\Rightarrow^{*}_{A}p, p\in F\}$ is the suffix language of $A$ with respect to the state $q$.

We have the following properties;

$$
\begin{align*}
&(L(A,q))_{w}=L(A,\delta(q,w))\text{ for $w\in\Sigma^{*}$}\tag{1}\\
&L(A,q_{0})=L(A)\tag{2}\\
&\varepsilon\in L(A,q)\iff q\in F\tag{3}
\end{align*}
$$

---

## Myhill–Nerode Theorem

**Theorem**: Given a language $L\in\Sigma^{*}$, then

$$
\begin{align*}
L\in\mathcal{L}_{3}\iff|\{L_{p}\}_{p\in\Sigma^{*}}|\lt\infty.
\end{align*}
$$

In other words, a type-three language must have a finite set of suffix languages. If a language has infinitely many suffix language, it cannot be a type-three language.

**Application**: Consider the language $L=\{a^{n}b^{n}\mid n\in\mathbb{N}\}$, we  will prove using Myhill-Nerode theorem that $L\notin\mathcal{L}_{3}$.

Let's us construct a suffix language of $L$ with respect to $a$, we have

$$
\begin{align*}
L_{a}=\{a^{n-1}b^{n}\mid n\ge1\}.
\end{align*}
$$

Let's repeat this process with $aa$ and $aaa$, we have 

$$
\begin{align*}
L_{aa}&=\{a^{n-2}b^{n}\mid n\ge2\}\\
L_{aaa}&=\{a^{n-3}b^{n}\mid n\ge3\}
\end{align*}
$$

Here we can see a pattern for $a^{k}$,

$$
\begin{align*}
L_{a^{k}}=\{a^{n-k}b^{n}\mid n\ge k, n\in\mathbb{N},k\in\mathbb{N}\}.
\end{align*}
$$

Thus we can see that $L$ has infinitely many suffix languages, as such, it cannot be aw type-three language.

**Application**: Let's consider a more complex language $L=\{w\in\{a,b\}^{*} \mid N_{a}(w) =0\mod2, N_{b}(w)=0\mod2\}$. That is, $L$ is a language containing words with even numbers of $a$ and even numbers of $b$.

First we consider the suffix language of $L$ with respect to $\varepsilon$, we have

$$
\begin{align*}
L_{\varepsilon}=L.
\end{align*}
$$

We consider the suffix language of $L$ with respect to $a$. We recognize that the number of $a$ in a word must now be odd while the number of $b$ remained even.

$$
\begin{align*}
L_{a}=\{w\in\{a,b\}^{*}\mid N_{a}(w)\equiv1\mod2, N_{b}(w)\equiv 0\mod 2\}.
\end{align*}
$$

Similarly for $b$,

$$
\begin{align*}
L_{b}=\{w\in\{a,b\}^{*}\mid N_{a}(w)\equiv0\mod2, N_{b}(w)\equiv 1\mod 2\}.
\end{align*}
$$

Lastly, we consider the suffix language of $L$ with respect to $ab$,

$$
\begin{align*}
L_{ab}=\{w\in\{a,b\}^{*}\mid N_{a}(w)\equiv1\mod2, N_{b}(w)\equiv 1\mod 2\}.
\end{align*}
$$

From this, we recognize that any word $w\in L$ will fall into one of these four suffix languages. For example $ba$ will fall into $L_{b}$. As such, $L$ has a finite number of suffix languages. Therefore, it must be a type-three language.

**Application**: Let's consider the language $L=\{w\in\{0,1\}^{*}\mid N_{0}(w)=N_{1}(w)\}$. We will try to show that $L$ is not a type-three language.

We construct the suffix language of $L$ with respect to $0$, we have

$$
\begin{align*}
L_{0}=\{1\}
\end{align*}
$$

Let's try to construct the suffix languages with respect to $00$ and $000$, we have

$$
\begin{align*}
L_{00}&=\{11\}\\
L_{000}&=\{111\}
\end{align*}
$$

We can generalize this with $0^{k}$ for $k\in\mathbb{N}$,

$$
\begin{align*}
L_{0^{k}} = \{1^{k}\}.
\end{align*}
$$

Here, we recognize that there are infinitely many $k$ for $0^{k}$, so $L$ has infinitely many suffix languages. As such, it cannot be a type-three language. 

---

## Minimal Deterministic Finite Automata

**Theorem**: Given a type-three language $L$ and a deterministic, finite automata $A=(Q,\Sigma,\delta,q_{0},F)$ such that $L(A)=L$, then $|\{L_{u}\}_{u\in\Sigma^{*}}\}|$ is at most $|Q|$.

---

**Definition**: We say that a deterministic, finite automata $A$ is a minimal deterministic finite automata if there is no other deterministic, finite automata $A'$ with less number of states such that $L(A)=L(A')$.

**Remarks**: We will discuss about the construction of the minimal deterministic, finite automata in the next section.

### Construction of Minimal Deterministic Finite Automata

**Remarks**: Given a deterministic, finite automata $A$, we will transform it into a minimal deterministic, finite automata in two steps;
- eliminating unreachable states,
- merging equivalent states.

Next, we will talk about reachability and equivalent states.

---

**Definition**: Given a deterministic, finite automata $A=(Q,\Sigma,\delta, q_{0},F)$, we say that a state $q\in Q$ is reachable if we can derive $q$ from $q_{0}$ via some $x\in\Sigma^{*}$. If we cannot derive $q$ from $q_{0}$, we say that $q$ is unreachable.

**Application**: We often construct a set $H$ which contains every reachable states in $A$. We use $H$ informally, and as a way to visualize our reachable states. Consider the deterministic finite automata 

$$
\begin{matrix*}
& & a & b\\
\rightarrow & q_{0} & q_{2} & q_{4}\\ 
\leftarrow & q_{1} & q_{3} & q_{0}\\ 
\leftarrow & q_{2} & q_{0} & q_{2}\\ 
& q_{3} & q_{1} & q_{2}\\ 
& q_{4} & q_{5} & q_{2}\\ 
\leftarrow& q_{5} & q_{4} & q_{2}\\ 
\end{matrix*}
$$

We start by constructing $H_{0}$ with is always $\{q_{0}\}$, then we construct $H_{1}$ from the union of $H_{0}$ and states reachable from $q_{0}$ in exactly one step;

$$
\begin{align*}
H_{0}&=\{q_{0}\}\\
H_{1}&=H_{0}\cup\{q_{2},q_{4}\}
\end{align*}
$$

We repeat this step for $H_{2}$. That is, we construct $H_{2}$ from the union of $H_{1}$ and those states reachable from $H_{1}$ in exactly one step;

$$
\begin{align*}
H_{0}&=\{q_{0}\}\\
H_{1}&=H_{0}\cup\{q_{2},q_{4}\}=\{q_{0},q_{2},q_{4}\}\\
H_{2}&=H_{1}\cup\{\underbrace {q_{2},q_{4}}_{q_{0}},\underbrace{q_{0},q_{2}}_{q_{2}},\underbrace {q_{2},q_{5}}_{q_{4}}\} =\{q_{0},q_{2},q_{4},q_{5}\}
\end{align*}
$$

We repeat this step for $H_{3}$ and we see that $H_{3}=H_{2}$. This is our stopping condition, once $H_{i}=H_{i-1}$ we have completed $H$, and we have;

$$
\begin{align*}
H_{0}&=\{q_{0}\}\\
H_{1}&=H_{0}\cup\{q_{2},q_{4}\}=\{q_{0},q_{2},q_{4}\}\\
H_{2}&=H_{1}\cup\{\underbrace {q_{2},q_{4}}_{q_{0}},\underbrace{q_{0},q_{2}}_{q_{2}},\underbrace {q_{2},q_{5}}_{q_{4}}\} =\{q_{0},q_{2},q_{4},q_{5}\}\\
H_{3}&=H_{2}\cup\{\underbrace {q_{2},q_{4}}_{q_{0}},\underbrace{q_{0},q_{2}}_{q_{2}},\underbrace {q_{2},q_{5}}_{q_{4}},\underbrace{q_{2},q_{4}}_{q_{5}}\} =\{q_{0},q_{2},q_{4},q_{5}\}\\
H&=H_{3}.
\end{align*}
$$

With this construction, we can conclude that states in $H$ are reachable, and $H\setminus Q$ contains unreachable states.

---

**Definition**: Given a deterministic, finite automata $A=(Q,\Sigma,\delta,q_{0},F)$, we say that two states $q,q'\in Q$ are indistinguishable if $L(A,q)=L(A,Q')$. We denote that $q,q'$ are indistinguishable with the notation $q\sim q'$. If $L(A,q)\ne L(A,q')$, we say that $q,q'$ are distinguishable.

**Remarks**: We will use Hopcroft's partition refinement algorithm to decide indistinguishable states in $A$.

#### Hopcroft's Partition Refinement

The goal of this algorithm is to represent state using partitions. In our application, we then choose one representative from each partition to include in our minimal, deterministic, finite automata.

The algorithm has four steps;
- define the set of reachable states
- define the initial partitions
- refine the partitions
- choose the representatives and construct the minimal, deterministic, finite automata 

**Application**: Let's demonstrate the steps with an example. Consider a deterministic, finite automata $A=(Q,\Sigma,\delta,q_{0},F)$ where 

$$
\begin{align*}
Q&=\{q_{0},q_{1},q_{2},q_{3},q_{4}\}\\
\Sigma&=\{a,b\}\\
F&=\{q_{1},q_{3}\}
\end{align*}
$$

and $\delta$ is given by the table;

$$
\begin{matrix*}
& & a & b\\
\rightarrow &q_{0} & q_{1}&q_{2}\\
\leftarrow &q_{1} & q_{0}&q_{4}\\
&q_{2} & q_{4}&q_{1}\\
\leftarrow &q_{3} & q_{1}&q_{0}\\
&q_{4} & q_{4}&q_{1}\\
\end{matrix*}
$$

First we define the set of reachable states. For the sake of brevity, we will skip this step. We have 

$$
\begin{align*}
H=\{q_{0},q_{1},q_{2},q_{4}\}.
\end{align*}
$$

Next, we define the initial partitions to be $F$ and $H\setminus F$,

$$
\begin{align*}
P_{1}&=F\cap H=\{q_{1}\}\\
P_{2}&=H\setminus P_{1}=\{q_{0},q_{2}, q_{4}\}\\
\end{align*}
$$

Next, we refine the partitions. The algorithm states that we can pick any arbitrary partitions and an input symbol $\alpha\in\Sigma$. So for the sake of demonstration, we pick $P_{2}$ and $a$, then for each state $q\in P_{2}$, we consider $\delta(q,a)$. If $\delta(q,a)\notin P_{2}$, we place it into a new partition.

$$
\begin{align*}
\delta(q_{0},a)&=q_{1}\\
\delta(q_{2},a)&=q_{4}\\
\delta(q_{4},a)&=q_{4}
\end{align*}
$$

We find that $q_{1}$ is not in $P_{2}$ We need to create a new partition $P_{3}=\{q_{1}\}$ but the partition $P_{1}$ already exist so we repeat this step, with $P_{2}$ and $b$.

$$
\begin{align*}
\delta(q_{0},b)&=q_{2}\\
\delta(q_{2},b)&=q_{1}\\
\delta(q_{4},b)&=q_{1}
\end{align*}
$$

Again, we do not need to create a new partition. Instead, we move on to $P_{1}$ with $a$;

$$
\begin{align*}
\delta(q_{1},a)=q_{0}
\end{align*}
$$

This time $q_{0}\notin P_{1}$ so we need a new partition $P_{3}=\{q_{0}\}$. We have

$$
\begin{align*}
P_{1}&=\{q_{1}\}\\
P_{2}&=\{\cancel{q_{0}},q_{2},q_{4}\}\\
P_{3}&=\{q_{0}\}
\end{align*}
$$

Thus we have finished the partition refinement step. Next, we construct a minimal, deterministic, finite automata from these partitions. We do this by choosing a representative from each partition.

For $P_{1}$ we can only pick $q_{1}$. For $P_{2}$ we can pick either $q_{2}$ or $q_{4}$. For $P_{3}$ we can only pick $q_{0}$.

$$
\begin{matrix*}
 &a & b \\
q_{0} & q_{1} & q_{2}\\
q_{1} & q_{0} &q_{2}\\
q_{2} & q_{2} & q_{1}
\end{matrix*}
$$

The representative of the partition which contains the original starting state will be the new starting state, in our case $q_{0}$. Similarly, the representatives of the partitions which contains the original accepting states will be the new accepting states. We have'


$$
\begin{matrix*}
 & &a & b \\
\rightarrow & q_{0} & q_{1} & q_{2}\\
\leftarrow & q_{1} & q_{0} &q_{2}\\
& q_{2} & q_{2} & q_{1}
\end{matrix*}
$$

---

## Pumping Lemma

**Theorem**: For every regular language $L$, there exists a natural number $n$ such that for all words $z\in L$ with $|z|\gt n$ can be expressed as $z=uvw$ and satisfying the following conditions
- $|uv|\le n$,
- $|v|\gt0$,
- $uv^{i}w\in L$ for $i\ge 0$.

**Application**: Consider the language $L=\{a^{j}b^{j}\mid j\ge 1\}$. We will show, using pumping lemma, that $L$ is not a regular language.

First, we assume that $L$ is a regular language. As such, there must exist a natural number $n$ such that every word $z\in L$ whose length is longer than $n$ can be written in the form $z=uvw$ and satisfy the conditions
- $|uv|\le n$,
- $|v|\gt0$,
- $uv^{i}w\in L$ for $i\ge0$

The important part here is to choose a counter-example  that violates one or more of the conditions. In our case, we pick the word $a^{m}b^{m}$ where $m\gt n$.

By condition $(1)$, we know that $|uv|\le n$. Since $m\gt n$, then $uv$ must contains only $a$. By condition $(2)$, we know that $|v|\gt0$ so $v$ must contains at least one $a$ symbol.

Now, we can construct our counter-example. By condition $(3)$, let's consider the case where $i=0$. Let $k\gt 0$ be the length of $v$, we have

$$
\begin{align*}
uv^{0}w &\in L\\
a^{m-k}b^{m}&\in L \tag{!}
\end{align*}
$$

Here, we have a contradiction. Since $k\gt 0$, then $m-k\ne m$, as such, the word $a^{m-k}b^{m}$ cannot be in $L$ and the condition $(3)$ is not unsatisfied. In fact, we can also find a contradiction for every $i\ge 2$.

Thus $L$ is not a regular language.

---