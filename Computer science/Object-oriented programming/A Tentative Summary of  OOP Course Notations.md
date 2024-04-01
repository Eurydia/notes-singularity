# A Tentative Summary of  OOP Course Notations

The summary attempts to collect notations in the object-oriented programming course.

## Data Types

### Primitive Data Types

The common primitive data types include, but are not limited to;
- **the set of natural number** excluding $0$, denoted by $\mathbb{N}\setminus\{0\}:=\{1,2,3,\ldots\}$,
- **the set of natural number** including $0$, denoted by $\mathbb{N}\cup\{0\}:=\{0,1,2,3,\ldots\}$,
- **The set of integers**, denoted by $\mathbb{Z}:=\{\ldots,-2,-1,0,1,2,\ldots\}$,
- **the set of real numbers**, denoted by $\mathbb{R}$,
- **the set of logical values**, denoted by $\mathbb{L}:=\{\text{true},\text{false}\}$, and
- **the set of characters**, denoted by $\mathbb{C}\text{h}$. (*There is not much information on the set of characters, so it would be nice to have additional clarification on the functions and operations defined on characters, even trivial ones.*)

### Sequence

Given an arbitrary type $T$, a sequence containing elements of type $T$ is denoted by "$T^{*}$." Informally, a sequence is an ordered collection of, possibly, infinitely many homogeneous elements. 

Explicit definition a sequence is possible with angle brackets; such as, $\langle t_{1}, t_{2},\ldots\rangle\in T^{*}$ for $t_{1},t_{2},\ldots\in T$.

Operations on a sequence $A\in T^{*}$ includes, but not limited to;
- concatenation, denoted by "$A\oplus B$" for $B\in T^{*}$,
- cardinality, denoted by "$|A|$", and
- indexing, denoted by "$A[n]$" for $n\in\mathbb{N}\setminus\{0\}$.

(*The index of a sequence always starts with $1$.*)

### Array

Given an arbitrary type $T$, an array with starting index $m$ of size $n-m+1$ containing elements of type $T$ is denoted by "$T^{m\ldots n}$", where $m,n\in\mathbb{Z}$ such that $m\le n$. It is possible to abbreviate "$T^{1\ldots n}$" to "$T^{n}$." Informally, an array is an ordered collection of finite homogeneous elements.

%% The explicit definition is possible with angle brackets; such as, $\langle t_{m}, t_{m+1},\ldots,t_{n-1}, t_{n}\rangle\in T^{m\ldots n}$ for $t_{m}, t_{m+1},\ldots,t_{n-1}, t_{n}\in T$.
 %%
 
Operations on an array $A\in T^{m\ldots n}$ includes, but not limited to;
- cardinality, denoted by "$|A|$", and
- indexing, denoted by "$A[k]$" for $k\in\mathbb{Z}$ such that $m\le k\le n$.

### Matrix

Given an arbitrary type $T$, a row-major matrix containing elements of type $T$ is denoted by "$T^{m\ldots n\times i\ldots j}$" where $m,n\in\mathbb{Z}$ denotes the index of the first and last row, and $i,j\in\mathbb{Z}$ denotes the index of the first and last column, respectively. It is also possible to abbreviate "$T^{1\ldots n\times 1\ldots j}$" to "$T^{n\times j}$."

Operations on a matrix $A\in T^{m\ldots n\times i\ldots j}$ includes, but not limited to;
- indexing, denoted by "$A[r,c]$" for $r,c\in\mathbb{Z}$ such that $m\le r\le n$ and $i\le c\le j$.

(*I could not find many relevant functions or operations on the matrix.*)

### Record

Given unique labels $l_{1},l_{2},\ldots$ and arbitrary types $T_{1},T_{2},\ldots$, a record is denoted by "$\text{rec}(l_{1}:T_{1}, l_{2}:T_{2},\ldots)$". Informally, a record is an unordered collection of, possibly, infinitely many label-type pairs.

Operations on a record $A\in\text{rec}(l : T)$ includes, but not limited to;
- assignment, denoted by "$A.l = t$" for  $t\in T$, and
- field access, denoted by "$A.l$."

(*I could not find a notation which explicitly defines an object of type record.*)

### Enumerator

Given an arbitrary type $T$, an enumerator containing elements of type $T$ is denoted by "$\text{enor}(T)$."

Operations on an enumerator $A\in\text{enor}(T)$ includes;
- cardinality, denoted by "$|A|$" for ,
- initialization, denoted by "$A.\text{first}()$",
- advance, denoted by "$A.\text{next}()$",
- peeking, denoted by "$A.\text{current}()$", and 
- has-ended, denoted by "$A.\text{end}()$".

## Notations

### Big Notation

The same notation applies to big concatenation $\bigoplus$, big conjunction $\bigwedge$, big disjunction $\bigvee$, big intersection $\bigcap$, big union $\bigcup$, etc.

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

### Max Notation

Given a totally-ordered set $(H,\le)$ and a function $f:[m,n]\to H$, where $m,n\in\mathbb{Z}$ such that $m\le n$, the expression

$$
\max\limits_{i=m}^{n} f(i)\tag{Expr. 6}
$$

evaluates to a $2-$ tuple "$(f(k),k)$" such that $h\le f(k)$ for every element $h\in H$, and $k\in\mathbb{Z}$ such that $m\le k\le n$.

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

