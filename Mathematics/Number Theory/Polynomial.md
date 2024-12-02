# Polynomial

**Definition**: We say that a mathematical expression is a polynomial if it contains only
- constant terms,
- a single variable,
- addition, subtraction, multiplication,
- exponentiation to a power in $\mathbb{N}$, and
- parentheses.

For example, the expression

$$
\begin{align*}
9x-3\sqrt{x}
\end{align*}
$$

is not a polynomial since $\sqrt{x}=x^{1/2}$ and not a natural exponent. We exclude division since we cannot guarantee that dividing two polynomials will result in another polynomial, in other words, polynomials are not closed under division.

**Definition**: We define the set $K[x]$ to be a set containing all polynomial where the constant term is a member of the set $K$ and it variable is $x$.

In our application, $K$ is one of the well-known mathematical sets $\mathbb{N}, \mathbb{Z}, \mathbb{Q},\mathbb{R}$, and so on. For example, $\mathbb{R}[k]$ contains every polynomial whose constant terms are real numbers and its variable is $k$.

**Definition**: We can express the same polynomial multiple ways, so we need a unique way to represent each polynomial. We define the canonical representation of a polynomial $p\in K[x]$ to be

$$
\begin{align*}
a_{n}x^{n}+a_{n-1}x^{n-1}+\ldots+a_{1}x+a_{0}
\end{align*}
$$

where $a_{i}\in K$ for $i=0,\ldots,n$ and $a_{n}\ne0$.

**Definition**: Based on the canonical form of a polynomial, we define the follow terminologies;

- We say that $a_{i}$'s are the coefficients of degree $i$ of the polynomial $p$.
- We say that $n$ is the degree of the polynomial $p$. We use the notation $\deg p$.
- We say that $a_{n}$ is the leading coefficient of the polynomial $p$.
- We say that $a_{0}$ is the constant term of the polynomial $p$.