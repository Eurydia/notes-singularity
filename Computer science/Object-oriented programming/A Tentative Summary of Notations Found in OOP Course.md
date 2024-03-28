# A Tentative Summary of Notations Found in OOP Course

The purpose is simple; to collect and document common notations found which the Object-oriented programming course.

## Background

The concept of data type is tightly tied to mathematics. When a programmer says "a variable is of type integer," a mathematician might say "the variable is an element of the set of integers." This sentiment is made even more apparent in the object-oriented course, where the behavior of a function or an operation on a data type is expressed through mathematical notations.

The first part of this summary discusses the common data types and the means in which we interact with them, while the second part discusses the notations used in conjunction with those data types.

## Data Types

The primitive data types are the familiar sets in mathematics. This part of the summary discusses the common data types, their definitions, and operations which are defined on those data types.

### Primitive Data Types

**Natural Numbers**

The set of natural numbers including $0$, denoted by $\mathbb{N}\cup\{0\}$, is defined as 
$\{0,1,2,3,\ldots\}$.  In some context, however, the set of natural number not include $0$, in such a case, it is better to denote the set of natural number by $\mathbb{N}\setminus\{0\}$.

**Integers**

The set of integers, denoted by $\mathbb{Z}$, is defined as $\{\ldots,-2,-1,0,1,2,\ldots\}$.

**Real Numbers**

The set of real numbers, denoted by $\mathbb{R}$, is often defined as a set which satisfies a some axioms, so it does not make sense to discuss the exact definition of the set of real numbers here.

**Boolean Values**

The set of Boolean values, denoted by $\mathbb{L}$, is defined as $\{\text{true},\text{false}\}$. One can interact Boolean values through logical connectives, such as, negation $\neg$, conjunction $\land$, disjunction $\lor$, etc.

**Characters**

The set of characters is denoted by $\mathbb{C}\text{h}$. 

### Sequence

A sequence is an ordered collection of, possibly infinite, homogenous elements. As such, elements of a sequence are traversed in the same order every time.

Given an arbitrary type $T$, a sequence $A$ containing elements of type $T$ is denoted by $A\in T^{*}$. One can explicitly define a sequence using angle brackets, such as, $A:=\langle t_{1}, t_{2},\ldots\rangle$ for $t_{1},t_{2},\ldots\in T$.

The concatenation operator $\oplus$ joins two sequences together by append the right operand to the end of the left operand.

The number of elements in a sequence $A$ is obtained through the cardinality operator $|A|$.

The $n$-th element of a sequence $A\in T^{*}$ can be queried using the index notation $A[n]$. It is generally accepted that $n$ should be a natural number as it is ambiguous to ask for a negative index, but whether $n\in\mathbb{N}\cup\{0\}$ or $n\in\mathbb{N}\setminus\{0\}$ will depend largely on the context.

### Matrix

### Record

### Enumerator

## Notations

### Summation Notation

Given an arbitrary non-empty set $H$, an identity element $0\in H$, and a binary relation $+:(H\times H)\to H$ such that $0 + h = h$ for every element $h\in H$, then for some $n\in\mathbb{N}$, the expression

$$
h_{1} + h_{2} + h_{3} + \ldots + h_{n} \tag{Expr.1}
$$

could be rewritten as 

$$
\sum\limits_{i=1}^{n} h_{i}. \tag{Expr.2}
$$

This notation is, essentially, the same as the **summation notation** found in mathematics, which can be read aloud as "the sum of $h_{1}$, $h_2$ , $h_{3}$ up to $h_{n}$."

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

If $\text{Expr.4}$ were to be expanded to its entirety, one could obtain an expression such as

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

The expression is read aloud as "the sum of $h_{i}$ for $i$ starting from $1$, and terminate once $p(h_{i})$ no longer holds." Thus, the verbose form of $\text{Expr.7}$ might only include the first few terms rather than all $n$ terms.

### Concatenation Notation

### Max Notation

Given am arbitrary non-empty set $G$, a partial ordering binary relation $\lt\subseteq G\times G$, and a minimal element $e\in G$ defined by $\lt$, that is, $e\lt g$ for every element $g\in G\setminus\{e\}$.

