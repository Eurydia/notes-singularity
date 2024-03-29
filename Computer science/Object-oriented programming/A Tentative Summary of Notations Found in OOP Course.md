# A Tentative Summary of Notations Found in the OOP Course

The purpose is simple; to collect and document common notations found which the Object-oriented programming course.

## Background

The concept of data type is tightly tied to mathematics. When a programmer says "A variable is of type integer," a mathematician might say "the variable is an element of the set of integers." This sentiment is made even more apparent in the object-oriented course, where the behavior of a function or an operation on a data type is expressed through mathematical notations.

The first part of this summary discusses the common data types and how we interact with them, while the second part discusses the notations used in conjunction with those data types.

## Data Types

The primitive data types are the familiar sets in mathematics. This part of the summary discusses the common data types, their definitions, and operations that are defined on those data types.

### Primitive Data Types

The common primitive data types includes, but not limited to;
- **the set of natural number** excluding $0$, denoted by $\mathbb{N}\setminus\{0\}:=\{1,2,3,\ldots\}$,
- **the set of natural number** including $0$, denoted by $\mathbb{N}\cup\{0\}:=\{0,1,2,3,\ldots\}$,
- **the set of integers**, denoted by $\mathbb{Z}:=\{\ldots,-2,-1,0,1,2,\ldots\}$,
- **the set of real numbers**, denoted by $\mathbb{R}$,
- **the set of logical values**, denoted by $\mathbb{L}:=\{\text{true},\text{false}\}$, and
- **the set of characters**, denoted by $\mathbb{C}\text{h}$. (*There is not much information on the set of characters, so it would be nice to have additional clarification on the functions and operations defined on characters, even trivial ones.*)

### Sequence

Given an arbitrary type $T$, a sequence containing elements of type $T$ is denoted by $T^{*}$. Informally, a sequence is an ordered collection of, possibly, infinitely many homogeneous elements. 

Explicit definition a sequence is possible with angle brackets; such as, $\langle t_{1}, t_{2},\ldots\rangle\in T^{*}$ for $t_{1},t_{2},\ldots\in T$.

Operations on a sequence includes, but not limited to;
- concatenation, denoted by $A\oplus B$ for sequences $A,B\in T^{*}$,
- cardinality, denoted by $|A|$ for a sequence $A\in T^{*}$, and
- indexing, denoted by $A[n]$ for $A\in T^{*}$ and $n\in\mathbb{N}\setminus\{0\}$.

(*The index of a sequence always starts with $1$.*)

### Array

Given an arbitrary type $T$, an array with starting index $m$ of size $n-m+1$ containing elements of type $T$ is denoted by $T^{m\ldots n}$, where $m,n\in\mathbb{Z}$ such that $m\le n$. It is possible to abbreviate $T^{1\ldots n}$ to $T^{n}$. Informally, an array is a ordered collection of finitely many homogeneous elements.

%% The explicit definition is possible with angle brackets; such as, $\langle t_{m}, t_{m+1},\ldots,t_{n-1}, t_{n}\rangle\in T^{m\ldots n}$ for $t_{m}, t_{m+1},\ldots,t_{n-1}, t_{n}\in T$.
 %%
 
Operations on a sequence includes, but not limited to;
- cardinality, denoted by $|A|$ for an array $A\in T^{m\ldots n}$, and
- indexing, denoted by $A[k]$ for $A\in T^{m\ldots n}$ and $k\in\mathbb{Z}$ such that $m\le k\le n$.

### Matrix

Given an arbitrary type $T$, a row-major matrix is denoted by $T^{m\ldots n\times i\ldots j}$ where $m,n\in\mathbb{Z}$ denotes the index of the first and last row, and $i,j\in\mathbb{Z}$ denotes the index of  the first and last column, respectively. It is also possible to abbreviate $T^{1\ldots n\times 1\ldots j}$ to $T^{n\times j}$.

Operations on a sequence includes, but not limited to;
- indexing the entry at $r-$th row and $c-$th column, denoted by $A[r,c]$ for $A\in T^{n\times j}$ where $r,c\in\mathbb{Z}$ such that $1\le r\le n$ and $1\le c\le j$.

(*I could not find many relevant functions or operations on the matrix either.*)

### Record

Given labels $l_{1},l_{2},\ldots$ and arbitrary types $T_{1},T_{2},\ldots$, a record is denoted by $\text{rec}(l_{1}:T_{1}, l_{2}:T_{2},\ldots)$. Informally, a record is an unordered collection of, possibly infinitely many, label-type pairs.

### Enumerator

## Notations

### Big Notation

#### Summation

Given an arbitrary non-empty set $H$, an identity element $0\in H$, and a binary relation $+:(H\times H)\to H$ such that $0 + h = h$ for every element $h\in H$, then for some $n\in\mathbb{N}$, the expression

$$
h_{1} + h_{2} + h_{3} + \ldots + h_{n} \tag{Expr.1}
$$

could be rewritten as 

$$
\sum\limits_{i=1}^{n} h_{i}. \tag{Expr.2}
$$

This notation is, essentially, the same as the **summation notation** found in mathematics, which can be read aloud as "the sum of $h_{1}$, $h_2$, $h_{3}$ up to $h_{n}$."

#### Conditional Summation Notation

Now, still on the set $H$, let's introduce a logical function $p:H\to\mathbb{L}$, where $\mathbb{L}:=\{\text{true},\text{false}\}$, one could place an additional condition on $\text{Expr.2}$;

$$
\sum\limits_{\substack{i=1\\ p(h_{i})}}^{n} h_{i}.\tag{Expr.3}
$$

With the addition of $p$, the intent is to sum only those $h_{i}$ for $i=1,2,3,\ldots,n$ such that $p(h_{i})$ holds. That is, $\text{Expr.3}$ is equivalent to

$$
\sum\limits_{i=1}^{n} \begin{cases}
h_{i} &\text{if } p(h_{i}) =\text{true},\\
0 &\text{if } p(h_{i}) =\text{false}.\\
\end{cases}\tag{Expr.4}
$$

If $\text{Expr. 4}$ were to be expanded to its entirety, one could obtain an expression such as

$$
0 + 0 + h_{3} + 0 + \ldots + h_{n}, \tag{Expr.5}
$$

instead of $\text{Expr.1}$. Thus, the conditional summation notation can be read aloud as "the sum of $h_{i}$ for integer $i$ starting from $1$ up to, and including $n$, such that $p(h_{i})$ holds."

#### Summation Until Notation

So far, only $n$ is placed above the summation notation, which could be interpreted as a form of shorthand in and of itself. If one were to rewrite $\text{Expr.2}$ by expanding $n$, one will obtain 

$$
\sum\limits_{i=1}^{i\le n} h_{i}. \tag{Expr.6}
$$

In other words, it is possible to place an arbitrary logical value in place of $n$, naturally, doing so will change the behavior of the notation. Consider once more the logical function $p$, then replace $n$ with it to obtain

$$
\sum\limits_{i=1}^{p(h_{i})}h_{i}. \tag{Expr.7}
$$

The expression is read aloud as "the sum of $h_{i}$ for $i$ starting from $1$, and terminate once $p(h_{i})$ no longer holds." Thus, the verbose form of $\text{Expr. 7}$ might only include the first few terms rather than all $n$ terms.

### Max Notation

Given am arbitrary non-empty set $G$, a partial ordering binary relation $\lt\subseteq G\times G$, and a minimal element $e\in G$ defined by $\lt$, that is, $e\lt g$ for every element $g\in G\setminus\{e\}$.

### Search Notation