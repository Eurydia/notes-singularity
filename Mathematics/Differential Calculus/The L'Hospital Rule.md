# The L'Hospital Rule

## Introduction to the L'Hospital Rule

We use the L'Hospital rule on indeterminate forms of limits to transform them into limits which we can evaluate easily via direct substitution.


**Theorem**: (L'Hospital rule) Given two [[extended real numbers]] $c,L\in\overline{\mathbb{R}}$, an open interval $I$ such that;
- $c\in I$ for two-sided limit, or 
- one of the endpoints of $I$ is $c$, 

and two functions $f,g:I\to\mathbb{R}$ such that;
- $f,g$ are differentiable on $I\setminus\{c\}$, 
- $g'(x)\ne0$ for all $x\in I\setminus\{c\}$, and
- $\lim\limits_{x\to c}{\frac{f'(x)}{g'(x)}}=L$.

If either 

$$\begin{align*}\lim\limits_{x\to c}{f(x)}=\lim\limits_{x\to c}{g(x)}=0\end{align*}$$

or 

$$\begin{align*}\lim\limits_{x\to c}{|f(x)|}=\lim\limits_{x\to c}{|g(x)|}=+\infty,\end{align*}$$

holds, then

$$\begin{align*}
\lim\limits_{x\to c}{\frac{f(x)}{g(x)}}=\lim\limits_{x\to c}{\frac{f'(x)}{g'(x)}}=L.
\end{align*}$$

**Remarks**: While we often apply this rule to the indeterminate limit of the form $\frac{0}{0}$ or $\frac{\pm\infty}{\pm\infty}$, we can reduce other indeterminate forms into $\frac{0}{0}$ or $\frac{\pm\infty}{\pm\infty}$ and apply the rule to it.

## Taylor's Polynomial

### Higher-order Derivative

**Definition**: Given a function $f:\mathbb{R}\to\mathbb{R}$ and a real number $a\in\text{int}D_{f}$, we say that $f$ is twice-differentiable at $a$, denoted with $f\in D^{2}(a)$ if 

$$\begin{align*}
\exists r\in(0,+\infty) : \forall{x\in B(a,r)} : f\in D(x)\land f'\in D(a)
\end{align*}$$

holds.

**Remarks**: Informally, we say that a function $f:\mathbb{R}\to\mathbb{R}$ is twice-differentiable at a point $a\in\text{int}D_{f}$, if $f$ is differentiable at $a$ and $f'$ is also differentiable at $a$.

**Definition**: Given a function $f:\mathbb{R}\to\mathbb{R}$ and a non-empty set 

$$\begin{align*}
D_{f^{(k)}}:=\{x\in\text{int}D_{f}\mid f\in D^{k}(x)\},
\end{align*}$$

we say the function $f^{(k)}:D_{f^{(k)}}\to\mathbb{R}$ is the $k^{\text{th}}$-order derivative of $f$. Similarly, we can also say $f$ is $k$ times differentiable.
