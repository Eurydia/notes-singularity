# A Tentative Summary of  OOP Course Notations

The summary attempts to collect notations in the object-oriented programming course.

## Data Types

### Primitive Data Types

The common primitive data types include, but are not limited to;
- **the set of natural number** excluding $0$, denoted by $\mathbb{N}^{+}:=\{1,2,3,\ldots\}$,
- **the set of natural number** including $0$, denoted by $\mathbb{N}:=\{0,1,2,3,\ldots\}$,
- **The set of integers**, denoted by $\mathbb{Z}:=\{\ldots,-2,-1,0,1,2,\ldots\}$,
- **the set of real numbers**, denoted by $\mathbb{R}$,
- **the set of rational numbers**, denoted by $\mathbb{Q}$,
- **the set of irrational numbers**, denoted by $\mathbb{Q}^{*}$ (*not to be confused with a sequence of rational numbers.*),
- **the set of logical values**, denoted by $\mathbb{L}:=\{\text{true},\text{false}\}$, and
- **the set of characters**, denoted by $\mathbb{C}\text{h}$. (*This data type does not have any function or operation.*)

### Sequence

Given an arbitrary type $T$, a sequence containing elements of type $T$ is denoted by $T^{*}$. Informally, a sequence is an ordered collection of elements of the same data type.

Explicit definition a sequence is possible with angle brackets; such as, $\langle t_{1}, t_{2},\ldots\rangle\in T^{*}$ for $t_{1},t_{2},\ldots\in T$.

Operations on a sequence $A,B\in T^{*}$ includes, but not limited to;
- **concatenation** $\oplus: (T^{*}\times T^{*})\to T^{*}$ joins two sequences together, for example $A\oplus B$,
- **cardinality** $|\bullet|:T^{*}\to\mathbb{N}$ yields the number of elements, for example $|A|$, and 
- **indexing** $\bullet[\bullet]:\mathbb{N}^{+}\to T$ yields an element at the specified index, for example $A[n]$ where $n\in\mathbb{N}^{+}$ and $n\le|A|$.

(*The index of a sequence always starts with $1$.*)

### String

A string is sequence of characters, as such, operations and functions on sequences behave in the same way with strings. Generally, the string data type is denoted by $\mathbb{S}$ or $\mathbb{C}\text{h}^{*}$.

### Array

Given an arbitrary type $T$, an array of length $m\in\mathbb{N}$ containing elements of type $T$ is denoted by $T^{m}$. Informally, an array is an ordered collection of finite elements of the same data type.

%% The explicit definition is possible with angle brackets; such as, $\langle t_{m}, t_{m+1},\ldots,t_{n-1}, t_{n}\rangle\in T^{m\ldots n}$ for $t_{m}, t_{m+1},\ldots,t_{n-1}, t_{n}\in T$.
 %%
 
Operations on an array $A\in T^{m}$ of length $m\in\mathbb{N}$ includes, but not limited to;
- **cardinality** $|\bullet|: T^{m}\to\mathbb{N}$ yields the number of elements, for example $|A|$, and 
- **indexing** $\bullet[\bullet]:\mathbb{N}^{+}\to T$ yields an element at the specified index, for example $A[n]$ where $n\in\mathbb{N}^{+}$ and $n\le m$.

### Record

Given unique labels $l_{1},l_{2},\ldots$ and arbitrary types $T_{1},T_{2},\ldots$, a record is denoted by $\text{rec}(l_{1}:T_{1}, l_{2}:T_{2},\ldots)$. Informally, a record is a collection of label-type pairs.

Operations on a record $A\in\text{rec}(l_{1}:T_{1}, l_{2}:T_{2},\ldots)$ includes, but not limited to;
- **assignment** assigns a value to the specified label, for example $A.l_{n}=t_{n}$, and
- **field access** yields a value associated with the specified label, for example $A.l_{n}$.

### Enumerator

Given an arbitrary type $T$, an enumerator of type $T$ is denoted by "$\text{enor}(T)$."

Operations on an enumerator $A\in\text{enor}(T)$ includes;
- **cardinality** $|\bullet|:\text{enor}(T)\to\mathbb{N}$ yields the number of elements, for example $|A|$, and 
- **initialization**$\bullet.\text{first}():\to NULL$$ initializes the enumeration, for example $A.\text{first}()$,
- **advance** $\bullet.\text{next}():\to NULL$ advances the enumeration, for example $A.\text{next}()$,
- **peeking** $\bullet.\text{current}():\to T$ yields the current element of the enumeration, for example $A.\text{current}()$, and 
- **has-ended** $\bullet.\text{end}\to\mathbb{L}$ queries whether the enumerator has finished enumeration or not, for example $A.\text{end}()$.

(*Using $NULL$ is definitely not right since **.first** and **.next** should returns the current state of the enumerator $(st: \{\text{abnorm}, \text{norm}\}, e: T, x:\text{enor}(T))$ or am I confusing it with **read**?* )

## Notations

#### Summation Notation

Given a monoid $(H,+,0)$, the expression

$$
\sum\limits_{i=m}^{n} h_{i} \tag{Expr. 1}
$$

is an abbreviation of

$$
h_{m}+h_{m+1}+\ldots + h_{n-1}+h_{n} \tag{Expr. 2}
$$

for $m,n\in\mathbb{Z}$ such that $m\le n$.

%%This notation is, essentially, the same as the **summation notation** found in mathematics, which can be read aloud as "the sum of $h_{1}$, $h_2$, $h_{3}$ up to $h_{n}$."%%

#### Conditional Summation Notation

Given the monoid $(H,+,0)$ and a logical function $p:H\to\mathbb{L}$, the expression

$$
\sum\limits_{\substack{i=m\\ p(h_{i})}}^{n} h_{i} \tag{Expr. 3}
$$

is an abbreviation of the expression

$$
\sum\limits_{i=m}^{n} \begin{cases}
h_{i} &\text{if } p(h_{i}) =\text{true},\\
0 &\text{otherwise}
\end{cases}\tag{Expr. 4}
$$

for $m,n\in\mathbb{Z}$ such that $m\le n$.

#### Summation Until Notation

Given a monoid $(H,+,0)$ and a logical function $p:H\to\mathbb{L}$, the expression

$$
\sum\limits_{i=m}^{p(h_{i})}h_{i} \tag{Expr.5}
$$

is interpreted as "the sum of $h_{i}$ for $i\in\mathbb{Z}$ starting from $m$, and stop when $p(h_{i})$ no longer holds."

### Big Notation

The same notation applies to big concatenation $\bigoplus$, big conjunction $\bigwedge$, big disjunction $\bigvee$, big intersection $\bigcap$, big union $\bigcup$, etc.

### Max Notation

Given a totally-ordered set $(H,\le)$ and a function $f:[m,n]\to H$, where $m,n\in\mathbb{Z}$ such that $m\le n$, the expression

$$
\text{MAX}_{i=m}^{n} f(i)\tag{Expr. 6}
$$

evaluates to a pair of values "$f(k),k$" such that $h\le f(k)$ for every element $h\in H$, and $k\in\mathbb{Z}$ such that $m\le k\le n$.

### Conditional Max Notation

Given a totally-ordered set $(H,\le)$, a logical function $p:[m,n]\to\mathbb{L}$, and a function $f:[m,n]\to H$, where $m,n\in\mathbb{Z}$ such that $m\le n$, the expression

$$
\max\limits_{\substack{i=m\\ p(i)}}^{n} f(i)\tag{Expr. 7}
$$

evaluates to a $3-$ tuple "$(l,f(k),k)$", where $l\in\mathbb{L}$, $l$ implies that $h\le f(k)$ for every element $h\in H$, and $k\in\mathbb{Z}$ such that $m\le k\le n$.

### Select Notation

Given a logical function $p:[m,n]\to\mathbb{L}$, where $m,n\in\mathbb{Z}$ such that $m\le n$, the expression

$$
\text{select}_{i=m}^{n}\;p(i)\tag{Expr. 8}
$$

evaluates to an integer $k$ where $\nexists i\in[m,k-1](i\in\mathbb{Z}) : p(i)$.

### Search Notation

Given a logical function $p:[m,n]\to\mathbb{L}$, where $m,n\in\mathbb{Z}$ such that $m\le n$, the expression

$$
\text{search}_{i=m}^{n}\;p(i)\tag{Expr. 9}
$$

evaluates to a $2-$tuple $(l,k)$, where $l\in\mathbb{L}$ and $l$ implies that $\nexists i\in[m,k-1](i\in\mathbb{Z}) : p(i)$.

