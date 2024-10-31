# Divisors

## Introduction to Divisors

**Definition**: Given two integers $a,b$, we  say that $a$ is a divisor of $b$ if there exists an integer $c$ such that $b=ac$. We use the notation $a\mid b$ to denote that $a$ is a divisor of $b$. Otherwise, we use the notation $a\not\mid b$.

**Definition**: Given two integers $a,b$, we say that $a$ is a proper divisor of $b$ if $a$ is a divisor of $b$ and $a\ne b$;

**Definition**: Given an integer $a\in\mathbb{Z}$, we say that the set 

$$
\begin{align*}
\{-1,1,-a,a\}
\end{align*}
$$

is the set of trivial divisors of $a$.

**Definition**: Given two integers $a,b\in\mathbb{Z}$, we say that $a$ and $b$ are associates if 

$$
\begin{align*}
a\mid b\land b\mid a.
\end{align*}
$$


### Properties of Divisibility

**Theorem**: Divisibility is reflexive;

$$
\begin{align*}
\forall{a\in\mathbb{Z}}:a\mid a.
\end{align*}
$$

**Theorem**: Divisibility is transitive;

$$
\begin{align*}
\forall{a,b,c\in\mathbb{Z}}:a\mid b\land b\mid c\implies a\mid c.
\end{align*}
$$

**Theorem**: Divisibility is antisymmetric;

$$
\begin{align*}
\forall{a,b\in\mathbb{Z}}:a\mid b\land b\mid a\implies a=b.
\end{align*}
$$

**Theorem**: Every integer is a divisor of zero;

$$
\begin{align*}
\forall{a\in\mathbb{Z}}:a\mid0.
\end{align*}
$$

**Theorem**: One is a divisor of every integer;

$$
\begin{align*}
\forall{a\in\mathbb{Z}}:1\mid a.
\end{align*}
$$

**Theorem**: Zero is a divisor only to itself;

$$
\begin{align*}
\forall{a\in\mathbb{Z}}:0\mid a\iff a=0.
\end{align*}
$$

**Theorem**: Given three integers $a,b,c\in\mathbb{Z}$ such that $a\mid b$ and $a\mid c$, then $a$ is also a divisor of $b+c$;

$$
\begin{align*}
\forall{a,b,c\in\mathbb{Z}}:a\mid b\land a\mid c\implies a\mid b+c.
\end{align*}
$$


**Theorem**: Given three integers $a,b,c\in\mathbb{Z}$ such that $a\mid b$ and $a\mid c$, then $a$ is also a divisor of $b-c$;

$$
\begin{align*}
\forall{a,b,c\in\mathbb{Z}}:a\mid b\land a\mid c\implies a\mid b-c.
\end{align*}
$$

**Theorem**: Given integers $a,b,c,d\in\mathbb{Z}$,

$$
\begin{align*}
a\mid b\land c\mid d\implies ac\mid bd
\end{align*}
$$

holds.

**Theorem**: Given two integers $a,b\in\mathbb{Z}$ such that $a\mid b$, then $a$ can be at most $b$;

$$
\begin{align*}
\forall{a,b\in\mathbb{Z}}:a\mid b\implies a\le b.
\end{align*}
$$

## Prime Numbers

**Definition**: Given a positive natural number $n\in\mathbb{N}$ such that $n\gt1$, we say that $n$ is a prime number if it only has trivial divisors.

**Definition**: Given a positive natural number $n\in\mathbb{Z}$ such that $n\gt1$, we say that $n$ is a composite number if it is not a prime number.

### Prime Counting

**Theorem**: There are infinitely many prime numbers.

**Definition**: We define a function $\pi:\mathbb{N}_{\gt0}\to\mathbb{N}$ to be a prime counting function, which accepts a positive natural number and counts how many prime numbers are there inclusively between one and $n$.

**Theorem**: (Prime counting theorem) The approximation for any given value of $\pi(n)$ is 

$$
\begin{align*}
\pi(n)\approx \frac{n}{\ln n}
\end{align*}
$$

or more precisely,

$$
\begin{align*}
\lim\limits_{n\to+\infty}{\frac{\pi(n)\cdot\ln n}{n}}=1.
\end{align*}
$$

### Twin Primes

**Definition**: Given a prime number $p$, we say that $p$ has a twin prime if $p-2$ or $p+2$ is also a prime number.

**Definition**: We say that an ordered pair of twin primes is a twin prime pair.

### Prime Factorization

**Theorem**: (Fundamental theorem of arithmetic) Given a positive integer $n\in\mathbb{Z}_{\gt0}$, we can uniquely express $n$ as a product prime numbers.

**Definition**:  We say that the product in the above-mentioned theorem is the prime factorization of $n$.

**Definition**: The canonical representation of a positive integer $n$ is

$$
\begin{align*}
n&=p_{1}^{n_{1}}\cdot p_{2}^{n_{2}}\cdot\ldots\cdot p_{k}^{_{n_{k}}}\\
&=\sum\limits_{i=1}^{k}p_{i}^{n_{i}}
\end{align*}
$$

where $p_{1}\lt p_{2}\lt\ldots\lt p_{k}$ are prime numbers and $n_{i}$ are positive integers.

## Divisor-related Functions

### Divisor Counting Function

**Definition**: Given a positive natural number $n\in\mathbb{N}_{\gt0}$, we say that $\tau(n)$ is the number of positive divisors of $n$.

$$
\begin{align*}
\tau(n)
\begin{cases*}
=1 & if $n=1$\\
=2 & if $n$ is a prime number\\
\ge 3 & if $n$ is a composie number
\end{cases*}
\end{align*}
$$

**Theorem**: Given a positive natural number $n\in\mathbb{N}_{\gt0}$, using the canonical representation $p_{1}^{n_{1}}\cdot p_{2}^{n_{2}}\cdot\ldots\cdot p_{k}^{_{n_{k}}}$, we have

$$
\begin{align*}
\tau(n)=(n_{1}+1)\cdot(n_{2}+1)\cdot\ldots\cdot(n_{k}+1).
\end{align*}
$$

**Theorem**: Given a positive natural number $n\in\mathbb{N}_{\gt0}$, then $\tau(n)$ is odd if and only if $n$ is a square number.

### Sum of Divisors Function

**Definition**: Given a positive natural number $n\in\mathbb{N}_{\gt0}$, we say that the function $\sigma(n)$ expresses the sum of positive divisors of $n$. 

**Theorem**: Given a positive natural number $n\in\mathbb{N}_{\gt0}$ with a canonical representation $p_{1}^{n_{1}}\cdot p_{2}^{n_{2}}\cdot\ldots\cdot p_{k}^{_{n_{k}}}$, then  

$$
\begin{align*}
\sigma(n)=\prod\limits_{i=1}^{k} \frac{p_{i}^{n_{i}+1}-1}{p_{i}-1}.
\end{align*}
$$

**Definition**: (Aliquot sum) Given a positive natural number $n\in\mathbb{N}_{\gt0}$, we say that the function $s(n)$ expresses the sum of proper divisors of $n$.

**Definition**: Given a positive natural number $n\in\mathbb{N}_{\gt0}$, we say that $n$ is a perfect number if

$$
\begin{align*}
s(n)=n.
\end{align*}
$$

**Definition**: Given two positive natural numbers $a,b\in\mathbb{N}_{\gt0}$, we say that $a$ and $b$ are amicable numbers if

$$
\begin{align*}
s(a)=b\land s(b)=a.
\end{align*}
$$