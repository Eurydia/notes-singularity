# Backgrounds and notations

This summary aims to collect notations in the object-oriented programming course. The motivation for this summary ensure that notations are well-defined and, more importantly, well-explained, so further applications are built on a solid foundation.

## Data types

Data type is a rather computer science-centric term, but in this summary, we will talk about them as in terms of sets to keep explanation brief and simple.

### Primitive data types

The common primitive data types include, but are not limited to;
- **the set of natural number** excluding $0$, denoted by $\mathbb{N}^{+}:=\{1,2,3,\ldots\}$,
- **the set of natural number** including $0$, denoted by $\mathbb{N}:=\{0,1,2,3,\ldots\}$,
- **the set of integers**, denoted by $\mathbb{Z}:=\{\ldots,-2,-1,0,1,2,\ldots\}$,
- **the set of real numbers**, denoted by $\mathbb{R}$,
- **the set of rational numbers**, denoted by $\mathbb{Q}$,
- **the set of irrational numbers**, denoted by $\mathbb{Q}^{*}$ (*not to be confused with a sequence of rational numbers.*),
- **the set of logical values**, denoted by $\mathbb{L}:=\{\text{true},\text{false}\}$, and
- **the set of characters**, denoted by $\mathbb{C}\text{h}$. (*This data type does not have any function or operation.*)

These sets serve as the basic building blocks for the complex data types.

### Sequences

A sequence, which contains elements of type $\mathbb{T}$, is denoted by $\mathbb{T}^{*}$. Elements of a sequence are explicitly listed using angle brackets; $\langle t_{1}, t_{2},\ldots, t_{n}\rangle\in\mathbb{T}^{*}$. Followed are the examples on the different sequence types;
- **natural number sequence**: $\langle1,2,3,4,5\rangle\in\mathbb{N}^{*}$,
- **Boolean sequence**: $\langle\top,\bot,\bot,\top\rangle\in\mathbb{L}^{*}$,
- **rational sequence**: $\langle \frac{1}{2}, \frac{1}{3},\frac{1}{4},\frac{1}{5} \rangle\in(\mathbb{Q})^{*}$, and
- **irrational sequence**: $\langle\pi,e,\sqrt{2}\rangle\in(\mathbb{Q}^{*})^{*}$.

Character sequences $(\mathbb{C}\text{h})^{*}$ are given special a name "string" and its type is abbreviated to $\mathbb{S}$. In addition, quotation marks are used to explicitly list elements of a string. For example $\text{``}Hello\text{''}$ is equivalent to $\langle H,e,l,l,o\rangle$ .

*(Here I wanted to emphasize that $\mathbb{T}$ is a generic type, and that, in practice, concrete types such as $\mathbb{N},\mathbb{L},\mathbb{R}$ are used instead.)*

Operations on a sequence include but are not limited to;

**Concatenation**

Concatenation is a binary operator
$\oplus: (\mathbb{T}^{*}\times \mathbb{T}^{*})\to \mathbb{T}^{*}$. It joins two sequences together to form a new sequence. For example, the concatenation of the sequences $A:=\langle a_{1},a_{2},\ldots,a_{n}\rangle$ and $B:=\langle b_{1},b_{2},\ldots,b_{m}\rangle$ is denoted by $A\oplus B =\langle a_{1},a_{2},\ldots,a_{n},b_{1},b_{2}\ldots, b_{m}\rangle$ where $A,B\in\mathbb{T}^{*}$.

*(The left operand is informally understood as the main sequence and the right operand is the secondary sequence, I think the explanation is intuitive, but it lacks formality.)*

**Cardinality**

Cardinality is a unary operator $|\bullet|:\mathbb{T}^{*}\to\mathbb{N}$. It yields the number of components in a sequence. For example, the cardinality of a sequence $A$ is denoted by $|A|$.

*(I really dislike using "$|\bullet|$" to denote the cardinality. I know there is a more intuitive and elegant way to express it, but I could not find it. I am also not happy about the use of the word "yield.")*

**Indexing**

Let $A:=\langle a_{1},a_{2},\ldots, a_{n}\rangle$ be a sequence and $k$ be a natural number where $1\le k\le n$. Indexing the $k-$th element of the sequence $A$ is denoted by $A[k]$.

*(Here, this operator implies too much on the behavior of sequences and I am not sure how much I should introduce. Generally, sequences are considered to be an ordered collection of items, which is why it is possible to "index" a particular element.)*

### Arrays

An array of length $m\in\mathbb{N}$ containing elements of type $\mathbb{T}$ is denoted by $\mathbb{T}^{m}$. Elements of an array are explicitly listed using angle brackets; $\langle t_{1}, t_{2},\ldots, t_{n}\rangle$. In practice, arrays generally have a fixed size, thus elements cannot be added to or removed from an array. The different notations are introduced for arrays and sequences to capture their real world properties. 

Operations on an array include but are not limited to;

**Cardinality** 

The cardinality operator on arrays behaves similarly to the cardinality operator on sequences. Since arrays contains a fixed number of elements, the cardinality of an array $A\in\mathbb{T}^{m}$, denoted by $|A|$, is always $m$.  

**Indexing**

Indexing arrays behaves similarly to indexing sequences.

### Records

A record is denoted by $\text{rec}(l_{1}:\mathbb{T}_{1}, l_{2}:\mathbb{T}_{2},\ldots,l_{n}:\mathbb{T}_{n})$ where $l_{1},l_{2},\ldots,l_{n}$ are unique field labels and $\mathbb{T}_{1},\mathbb{T}_{2},\ldots,\mathbb{T}_{n}$ are types. Followed are the examples on the different definitions of record;
- $\text{rec}(re:2,im:9)$ belongs to the record type $\text{rec}(re:\mathbb{R},im:\mathbb{R})$, and
- $\text{rec}(name: \text{``}John\text{''}, age:28)$ belongs to the record type $\text{rec}(name:\mathbb{S},age:\mathbb{N})$.

Operations on a record include but are not limited to;

**Field access**

Consider the record $a:=\text{rec}\left(x:10\right)$ where $a\in\text{rec}(x:\mathbb{N})$, we access the label $x$ of $a$ by $a.x$ where $(a.x)\in\mathbb{N}$.

*(This explanation is not clear enough, essentially, a record could be thought of as a collection of label-value pairs. On a record, the label is used to access its corresponding value. In a way the record itself is a mapping which assigns a value to each of its label.)*

**Field assignment**

Field assignment updates the value of a label on a record with a new value. For example, consider the record $a:=\text{rec}(x:10)$ where $a\in\text{rec}(x:\mathbb{N})$, let $a.x:=9$ denote assigning $9$ to the label $x$ of the record $a$, doing so generate a new record $b\in\text{rec}(x:\mathbb{N})$ where $b.x=9$.

### Enumerators

An enumerator, which contains elements of type $\mathbb{T}$, is denoted by $\text{enor}(\mathbb{T})$. In practice, an enumerator gives access to a small piece of data at time, once this piece of data is processed, the programmer may choose to move forward onto the next piece of data. However, an enumerator does not move backward. Once a piece of data is consumed, it is effectively removed from memory, thus making enumerators highly memory-efficient.

Due to their nature, there is no motivation to introduce a notation  which would explicitly list elements of an enumerator, but to illustrate its application, let's assume we have the following enumerator $A:=\{1,2,3,1,2,3\}$ where $A\in\text{enor}(\mathbb{N})$, the sum of $A$ is obtained with $\sum\limits_{a\in A}a$, which expands to $1+2+3+1+2+3$.

Operations on an enumerator include but are not limit to;

**Cardinality**

For the sake of simplicity, cardinality of an enumerator is known, even though such information might not be possible in practice. Cardinality of an enumerator $A\in\text{enor}(\mathbb{T})$ is denoted by $|A|$.

## Interval-based Notations

The interval-based notations share a common component; there is an interval $[m,n]\subseteq\mathbb{Z}$.

### Summation Notation

Given a monoid $(H,+,0)$, an interval $[m,n]\subseteq\mathbb{Z}$, and a function $f:[m,n]\to H$, the notation

$$
\sum\limits_{i=m}^{n} f(i)
$$

expands to

$$
f(m)+f(m+1)+\ldots+f(n-1)+f(n).
$$

### Conditional Summation Notation

Given a monoid $(H,+,0)$, an interval $[m,n]\subseteq\mathbb{Z}$, a function $f:[m,n]\to H$, and a logical function $p:[m,n]\to\mathbb{L}$, the notation

$$
\sum\limits_{\substack{i=m\\ p(i)}}^{n} f(i)
$$

expands to

$$
\sum\limits_{i=m}^{n} \begin{cases}
f(i) &\text{if } p(i)=true,\\
0 &\text{otherwise}.
\end{cases}
$$

### Summation Until Notation

Given a monoid $(H,+,0)$, an interval $[m,n]\subseteq\mathbb{Z}$, a function $f:[m,n]\to H$, and a logical function $p:[m,n]\to\mathbb{L}$, the notation

$$
\sum\limits_{i=m}^{p(i)} f(i)
$$

expands to

$$
\sum\limits_{i=m}^{k} f(i)
$$

where $k=\min\{i\in[m,n] :p(i)=true\}$. That is, the summation runs until the smallest index $k$ in which $p(k+1)$ does not hold.

### Big Notations

The same notational variants applies to big concatenation $\bigoplus$, big conjunction $\bigwedge$, big disjunction $\bigvee$, big intersection $\bigcap$, big union $\bigcup$, etc.

For example, given an interval $[m,n]\subseteq\mathbb{Z}$, a function $f:[m,n]\to(\mathbb{T}^{*})$, and a logical function $p:[m,n]\to\mathbb{L}$, the notation for conditional concatenation is written as;

$$
\bigoplus_{\substack {i=m\\ p(i)}}^{n} f(i)
$$

*(I believe this section is no longer necessary since we primarily use the term monoids already.)*

### Max Notation

Given a totally-ordered set $(H,\le)$, an interval $[m,n]\subseteq\mathbb{Z}$, and a function $f:[m,n]\to H$, the notation

$$
\max\limits_{i=m}^{n} f(i)
$$

evaluates to a pair 

$$\left(f(k),k\right)$$ 

where $f(k)\in H$ and $k\in[m,n]$ such that $f(k)=\max H$.

*(There is no precise definition to the exact behavior of $k$, so it is not possible to say whether $k$ is the smallest or the largest index for which $f(k)=\max H$.)*

### Conditional Max Notation

Given a totally-ordered set $(H,\le)$, an interval $[m,n]\subseteq\mathbb{Z}$, a function $f:[m,n]\to H$, and a logical function $p:[m,n]\to\mathbb{L}$, the notation

$$
\max\limits_{\substack{i=m\\ p(i)}}^{n} f(i)
$$

evaluates to a triple 

$$(l,f(k),k)$$

where $l\in\mathbb{L}$, $f(k)\in H$, and $k\in[m,n]$ such that $(l=true)\implies f(k)=\max H\land p(k)=true$.

### Select Notation

Given an interval $[m,n]\subseteq\mathbb{Z}$ and a logical function $p:[m,n]\to\mathbb{L}$, there exists an index $r\in[m,n]$ for which $p(r)$ holds. The notation

$$
\mathrel{\substack{n\\\text{select}\\ i=m}} p(i)
$$

evaluates to $k$ where $k\in[m,n]$ such that $k=\max\{i\in[m,n] : p(i)=true\}$.

### Search Notation

Given an interval $[m,n]\subseteq\mathbb{Z}$ and a logical function $p:[m,n]\to\mathbb{L}$, the notation

$$
\mathrel{\substack{n\\\text{search}\\ i=m}} p(i)
$$

evaluates to a pair 

$$(l,k)$$

where $l\in\mathbb{L}$ and $k\in[m,n]$ such that $(l=true)\implies k=\max\{i\in[m,n] : p(i)=true\}$.

## Enumerator-based Notations

The enumerator-based notations share a common component; there is an enumerator, which contains elements of an arbitrary type $\mathbb{E}$,

### Summation Notation

Given a monoid $(H,+,0)$, an enumerator $t\in\text{enor}(\mathbb{E})$, and a function $f:\mathbb{E}\to H$, the notation

$$
\sum\limits_{e\in t} f(e)
$$

expands to

$$
f(e_{1})+f(e_{2})+\ldots
$$

### Conditional Summation Notation

Given a monoid $(H,+,0)$, an enumerator $t\in\text{enor}(\mathbb{E})$, a function $f:\mathbb{E}\to H$, and a logical function $p:\mathbb{E}\to\mathbb{L}$, the notation

$$
\sum\limits_{\substack{e\in t\\ p(e)}} f(e)
$$

expands to

$$
\sum\limits_{e\in t} \begin{cases}
f(e) &\text{if } p(e),\\
0 &\text{otherwise}.
\end{cases}
$$

### Summation Until Notation

Given a monoid $(H,+,0)$, an enumerator $t\in\text{enor}(\mathbb{E})$, a function $f:\mathbb{E}\to H$, and a logical function $p:\mathbb{E}\to\mathbb{L}$, the notation

$$
\sum\limits_{e\in t}^{p(e)} f(e)
$$

evaluates to a pair

$$
(x, t')
$$

where $x\in H$ and $t'\in\text{enor}(\mathbb{E})$ such that $x$ is the sum elements in $t$ and $t'$ contains the unconsumed elements of $t$.

*(Say, $p(e_{k+1})$, where $e_{k+1}$ is the $k+1-$th element of $t$, does not hold, then the sum $x$ will be the sum of the first $k$ elements, and $t'$ contains elements of $t$ except the first $k$ elements.)*

### Max Notation

Given a totally-ordered set $(H,\le)$, an enumerator $t\in\text{enor}(\mathbb{E})$, and a function $f:\mathbb{E}\to H$, the notation

$$
\max\limits_{e\in t} f(e)
$$

evaluates to a pair

$$\left(f(e),e\right)$$ 

where $f(e)\in H$ and $e\in\mathbb{E}$ such that $f(e)=\max H$.

### Conditional Max Notation

Given a totally-ordered set $(H,\le)$, an enumerator $t\in\text{enor}(\mathbb{E})$, a function $f:\mathbb{E}\to H$, and a logical function $p:[m,n]\to\mathbb{L}$, the notation

$$
\max\limits_{\substack{e\in t\\ p(e)}} f(e)
$$

evaluates to a triple 

$$(l,f(e),e)$$

where $l\in\mathbb{L}$, $f(e)\in H$, and $e\in\mathbb{E}$ such that $l\implies f(e)=\max H$.

### Select Notation

Given an enumerator $t\in\text{enor}(\mathbb{E})$ and a logical function $p:\mathbb{E}\to\mathbb{L}$, there exists an element $r\in t$ for which $p(r)$ holds. The notation

$$
\mathrel{\substack{\text{select}\\ e\in t}} p(e)
$$

evaluates to pair

$$(x, t')$$

where $x\in\mathbb{E}$ and $t'\in\text{enor}(E)$ such that $x$ is the first element for which $p(x)$ holds and $t'$ contains the unconsumed elements of $t$.

### Search Notation

Given an enumerator $t\in\text{enor}(\mathbb{E})$ and a logical function $p:\mathbb{E}\to\mathbb{L}$, the notation

$$
\mathrel{\substack{\text{search}\\ e\in t}} p(e)
$$

evaluates to a triple

$$(l,f(e), t')$$

where $l\in\mathbb{L}$, $f(e)\in H$, and $t'\in\text{enor}(\mathbb{E})$ such that $(l=true)\implies f(e)=\max H\land p(e)=true$ and $t'$ contains the unconsumed elements of $t$.

