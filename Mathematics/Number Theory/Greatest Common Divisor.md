# Greatest Common Divisor

## Introduction to Greatest Common Divisor

**Definition**: Given two integers $a,b\in\mathbb{Z}$ and a natural number $c\in\mathbb{N}$, we say that $c$ is the *greatest common divisor of $a,b$* if

$$
\begin{align*}
c\mid a\land c\mid b\land\forall{d\in\mathbb{N}}:d\mid a\land d\mid b\implies d\mid c,
\end{align*}
$$

and we use the notation $\gcd(a,b)$ to denote the greatest common divisor of $a,b$.

**Definition**: Given two integers $a,b\in\mathbb{Z}$ and a natural number $c\in\mathbb{N}$, we say that $c$ is the *least common multiple of $a,b$* if

$$
\begin{align*}
a\mid c\land b\mid c\land\forall{d\in\mathbb{N}}:a\mid d\land b\mid d\implies c\mid d,
\end{align*}
$$

and we use the notation $\text{lcm}(a,b)$ to denote the least common multiple of $a,b$.

### Properties of Greatest Common Divisor

**Theorem**: Given a natural number $a\in\mathbb{N}$, the greatest common divisor of $a$ is itself;

$$
\begin{align*}
\forall{a\in\mathbb{N}}: \gcd(a,a)=a.
\end{align*}
$$

**Theorem**: Given two integers $a,b\in\mathbb{Z}$, the greatest common divisor of $a,b$ is equal to the greatest common divisor of $b,a$;

$$
\begin{align*}
\forall{a,b\in\mathbb{Z}}:\gcd(a,b)=\gcd(b,a).
\end{align*}
$$

In other words, the greatest common divisor operation is commutative.

**Theorem**: Given a natural number $a\in\mathbb{N}$, the greatest common divisor of $a$ and zero is $a$;

$$
\begin{align*}
\forall{a\in\mathbb{N}}:\gcd(a,0)=\gcd(0,a)=a.
\end{align*}
$$

**Theorem**: Given two natural numbers $a,b\in\mathbb{N}$ such that $a\mid b$, the greatest common divisor between $a,b$ is $a$;

$$
\begin{align*}
\forall{a,b\in\mathbb{N}}:a\mid b\implies\gcd(a,b)=\gcd(b,a)=a.
\end{align*}
$$

**Theorem**: Given two integers $a,b\in\mathbb{Z}$ such that $a,b\lt0$, the greatest common divisor of $a,b$ is equal to the greatest common divisor of their absolute values;

$$
\begin{align*}
\forall{a,b\in\mathbb{Z}}:a\lt0\land b\lt0\implies\gcd(a,b)=\gcd(|a|,|b|).
\end{align*}
$$