# Probability sampling

Let $(\Omega, \mathcal{F}, P)$ be a [[Discrete probability space|discrete probability space]].

Probability sampling involves selecting members from a population to form [[Singularity/Mathematics/Discrete probability theory/Sample|samples]] where each member has an equal chance of being chosen. 

Different methods of probability sampling exist, each with its own characteristics and formulas for determining sample sizes.

## Unordered probability sampling with replacement

In this method, each element in a finite set $U$ can be chosen multiple times without regard to order. 

If $n=|U|$, the number of $k$-element samples is given by the formula

$$\binom{n + k - 1}{k} = \binom{n + k - 1}{n - 1}.$$

For example, let $U=\{A,B,C,D\}$, the number of $2$-element samples is $10$, and the possible combinations are:

$$
\begin{matrix}
\{A,A\} & \{A,B\} & \{A,C\} & \{A,D\}\\
        & \{B,B\} & \{B,C\} & \{B,D\}\\ 
        &         & \{C,C\} & \{C,D\}\\ 
        &         &         & \{D,D\}\\ 
\end{matrix}
$$

## Unordered sampling without replacement

In this method, each element in a set $U$ each element can be chosen at most once without regard to order.

If $n=|U|$, the number of $k$-element samples where $k\le n$ is given by the formula

$$\binom{n}{k}.$$

If $k \gt n$, the number of samples is $1$ which is the empty set.
In other words, it is not possible to form $6$-element sample from a universe of only $4$ elements without repeating elements.

For example, let $U=\{A,B,C,D\}$, the number of $2$-element samples is $6$, and the possible combinations are:

$$
\begin{matrix}
 & \{A,B\} & \{A,C\} & \{A,D\}\\
 &         & \{B,C\} & \{B,D\}\\ 
 &         &         & \{C,D\}\\ 
\end{matrix}
$$

## Ordered probability sampling without replacement

In this method, each element in a set $U$ can be chosen at most once, and the order of selection matters.

If $n=|U|$, the number of $k$-element samples where $k\le n$ is given by the formula 

$$\frac{n!}{(n-k)!}.$$

If $k \gt n$, the number of samples is $1$ which is the empty set.
In other words, it is not possible to form $6$-element sample from a universe of only $4$ elements without repeating elements.

For example, let $U=\{A,B,C,D\}$, the number of $2$-element samples is $12$, and the possible combinations are:

$$
\begin{matrix}
      & (A,B) & (A,C) & (A,D)\\
(B,A) &       & (B,C) & (B,D)\\ 
(C,A) & (C,B) &       & (C,D)\\ 
(D,A) & (D,B) & (D,C) &
\end{matrix}
$$

## Ordered probability sampling with replacement

In this method, each element in a set $U$ can chosen multiple times, and the order of selection matters.

If $n=|U|$, the number of $k$-samples is given by the formula

$$n^{k}.$$

For example, let $U=\{A,B,C,D\}$, the number of $2$-element samples is $16$, and the possible combinations are:

$$
\begin{matrix}
(A,A) & (A,B) & (A,C) & (A,D)\\
(B,A) & (B,B) & (B,C) & (B,D)\\ 
(C,A) & (C,B) & (C,C) & (C,D)\\ 
(D,A) & (D,B) & (D,C) & (D,D)
\end{matrix}
$$