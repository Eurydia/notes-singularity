# Background and Notations

The purpose is simple; to collect and document common notations found which the Object-oriented programming course.

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

### Conditional Summation Notation

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

### Summation Until Notation

So far, only $n$ is placed above the summation notation, which could be interpreted as a form of shorthand in and of itself. If one were to rewrite $\text{Expr.2}$ by expanding $n$, one will obtain 

$$
\sum\limits_{i=1}^{i\le n} h_{i}. \tag{Expr.6}
$$

In other words, it is possible to place an arbitrary logical value in place of $n$, naturally, doing so will change the behavior of the notation. Consider once more the logical function $p$, then replace $n$ with it to obtain

$$
\sum\limits_{i=1}^{p(h_{i})}h_{i}. \tag{Expr.7}
$$

The expression is read aloud as "the sum of $h_{i}$ for $i$ starting from $1$, and terminate once $p(h_{i})$ no longer holds." Thus, the verbose form of $\text{Expr.7}$ might only include the first few terms rather than all $n$ terms.

### Max Notation

