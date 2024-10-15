# Grammar

## Chomsky's Classification of Grammars

**Definition**: Given a grammar $G=\langle N,\Sigma,P,S\rangle$, we classify $G$ based on $P$.

**Definition**: We say that $G$ is a type-zero grammar without any restriction. This class of grammar is called *phrase-structured grammar*.

**Definition**: We say that $G$ is a type-one grammar if all production rule in $P$ is in the form $(u_{1}Au_{2},u_{1}vu_{2})$ where $u_{1},u_{2},v\in(N\cup\Sigma)^{*}, A\in N$, and $v\ne\epsilon$. This class of grammar is called *context-sensitive grammar*.

In addition, $P$ may contain the production rule $(S,\epsilon)$ without violating the above-mentioned rule, however, $S$ must not appear on the right-hand side of any other production rule. We call this exception "restricted $\epsilon$ rule."

**Definition**: We say that $G$ is a type-two grammar if all production rule in $P$ is in the form $(A, v)$ where $A\in N$ and $v\in(N\cup\Sigma)^{*}$. This class of grammar is called *context-free grammar.*

**Definition**: We say that $G$ is a type-three grammar if all production rule in $P$ is in the form $(A,uB)$ or $(A,u)$ where $A,B\in N$ and $u\in\Sigma^{*}$. This class of grammar is called *regular grammar.*

**Definition**: We denote each class of grammar using $\mathcal{G}_{n}$ for $n=0,1,2,3$.

**Theorem**: Given a grammar $G$, the possible classification of $G$ is finite. Namely;
- $G$ is a type-three, -two, -one, and -zero grammar: production rules are in the form of $\mathcal{G}_{3}$ and RER holds.
- $G$ is a type-three, -two, and -zero grammar: production rules are in the form of $\mathcal{G}_{3}$ but RER does not hold.
- $G$ is a type-two, -one, and -zero grammar: production rules are in the in form of $\mathcal{G}_{2}$ and RER holds.
- $G$ is a type-two and -zero grammar: production rules are in the in form of $\mathcal{G}_{2}$ and RER does not hold.
- $G$ is a type-one and -zero grammar: production rules are in the form of $\mathcal{G}_{1}$ and RER holds.
- $G$ is a type-zero grammar.

## Chomsky's Classification of Languages

**Definition**: There are four classification of languages based on the underlying grammar. We use $\mathcal{L}_{n}$ for $n=0,1,2,3$ to denote the language type. More formally, $\mathcal{L}_{n}:=\{L|\exists G\in G_{n} : L = L(G)\}$.

**Definition**: We say that languages generated from a type-zero grammar is a *recursively-enumerable language*.

**Definition**: We say that languages generated from a type-one grammar is a *context-sensitive language.*

**Definition**: We say that languages generated from a type-two grammar is a *context-free language.*

**Definition**: We say that languages generated from a type-three grammar is a *regular language.*

## Chomsky's Hierarchy

Based from the definition of the classification of grammars, we can observer that $\mathcal{G}_{3}\subseteq\mathcal{G}_{2}\subseteq\mathcal{G}_{0}$ and $\mathcal{G}_{1}\subseteq\mathcal{G}_{0}$. From this observation, we have

**Theorem**: Chomsky's hierarchy

$$
\mathcal{L}_{3}\subset\mathcal{L}_{2}\subset\mathcal{L}_{1}\subset\mathcal{L}_{0}.
$$

## Equivalent Grammars and Languages

We can observe that a single grammar generates a single language, but a language can be generated from multiple grammars.

**Definition**: Given two grammars $G_{1},G_{2}$, we say that $G_{1},G_{2}$ are equivalent if $L(G_{1})=L(G_{2})$. In other words, $G_{1},G_{2}$ are equivalent if they generate the same language.

**Definition**: Given two languages $L_{1},L_{2}$, we say that $L_{1},L_{2}$ are weakly equivalent if they differ by  at most $\epsilon$.

**Definition**: Given two grammars $G_{1},G_{2}$, we say that they are weakly equivalent if they generate weakly equivalent languages.

## Elimination of Terminals from LHS of Production Rules

**Theorem**: For any grammar $G=\langle N,\Sigma, P, S\rangle$, there exists an equivalent grammar $G'=\langle N',\Sigma, P',S\rangle$ of the same classification with the property; $x\in(N')^{+}$ for all $(x,y)\in P'$.

Informally, the left-hand side of production rules of the equivalent grammar $G'$ only contain non-terminal symbols.

## Closure Properties

**Definition**: We say that the union operation, concatenation operation, and iterative closure are regular operations.

**Theorem**: The language class $\mathcal{L}_{n}$ for $n=0,1,2,3$ is closed under the regular operations.