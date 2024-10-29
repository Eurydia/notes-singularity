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

### Introduction to Taylor's Polynomial

**Definition**: Given a real number $a\in\mathbb{R}$ and a function $f:\mathbb{R}\to\mathbb{R}$ such $f$ is $n$ times differentiable at $a$, we define the $n^{\text{th}}$-term Taylor's polynomial of the function $f$ with the center point $a$ to be

$$\begin{align*}
T_{n,a}&:=\sum\limits_{k=0}^{n} \frac{f^{(k)}(a)}{k!}(x-a)^{k}.
\end{align*}$$

**Theorem**: (Taylor's formula) Given an open interval $I\subseteq\mathbb{R}$, a real number $a\in I$, and a function $f:I\to\mathbb{R}$ such that $f$ is $n\in\mathbb{N}_{\ge0}$ times differentiable at $a$, then $\forall x\in I\setminus\{a\}$, there exists a real number $\xi$ between $x$ and $a$ such that

$$\begin{align*}
f(x)-T_{n-1,a}=\frac{f^{(n)}(\xi)}{n!}(x-a)^{n}.
\end{align*}$$

**Remark**: We can observe that in the case $n=0$, the Taylor's formula coincide with [[Lagrange's mean-value theorem]].

## Concavity

### Definition of Concavity

**Definition**: Given an interval $I\subseteq\mathbb{R}$ and a function $f:I\to\mathbb{R}$, then we say that the function $f$ is $\text{``concave''}$ if 

$$
\begin{align*}
\forall x,y\in I : \forall{\alpha\in[0,1]} : f((1-\alpha)x+\alpha y)\ge(1-\alpha)f(x)+\alpha f(y).
\end{align*}
$$

**Definition**: Given an interval $I\subseteq\mathbb{R}$, and a function $f:I\to\mathbb{R}$, we say that the function $f$ is a $\text{``strict concave''}$ function if

$$
\begin{align*}
\forall x,y\in I :(x\ne y)\land(\forall{\alpha\in(0,1)} : f((1-\alpha)x+\alpha y)\gt(1-\alpha)f(x)+\alpha f(y)).
\end{align*}
$$

### Definition of Convexity

**Remarks**: The term $\text{``convexity"}$ is an alternative term for $\text{``concave upward."}$ As such the definition for convex function and strict convex function are similar to the definition of concave functions.


**Definition**: Given an interval $I\subseteq\mathbb{R}$ and a function $f:I\to\mathbb{R}$, then we say that the function $f$ is $\text{``convex''}$ if for any two real numbers $x,y\in I$, and any real number $\alpha\in[0,1]$

$$
\begin{align*}
f((1-\alpha)x+\alpha y)\le(1-\alpha)f(x)+\alpha f(y)
\end{align*}
$$

holds.

**Definition**: Given an interval $I\subseteq\mathbb{R}$, and a function $f:I\to\mathbb{R}$, we say that the function $f$ is a $\text{``strict convex''}$ function if for any two real numbers $x,y\in I$ such that $x\ne y$,  and any real number $\alpha\in(0,1)$

$$
\begin{align*}
f((1-\alpha)x+\alpha y)\lt(1-\alpha)f(x)+\alpha f(y))
\end{align*}
$$

holds.

#### Theorems of Concavity

##### Theorems of Concavity on First-order Derivatives

**Theorems**: Given an interval $I\subseteq\mathbb{R}$ and a everywhere-continuous, everywhere-differentiable function $f:I\to\mathbb{R}$, the function $f$ is concave on $I$ if the first-order derivative of $f$ is strictly increasing.

**Theorem**: Given an interval $I\subseteq\mathbb{R}$ and a function $f:I\to\mathbb{R}$ which is continuous and differentiable on the interval $I$, the function $f$ is convex on $I$ if the first-order derivative of $f$ is strictly decreasing.

##### Theorems of Concavity on Second-order Derivatives

**Theorem**: Given a real interval $I\subseteq\mathbb{R}$ and a function $f:I\to\mathbb{R}$, which is continuous and twice-differentiable on the interval $I$, the function $f$ is convex on $I$ if 

$$
\begin{align*}
\forall{x\in\text{int}I}:f''(x)\gt0.
\end{align*}
$$

**Theorem**: Given a real interval $I\subseteq\mathbb{R}$, and a function $f:I\to\mathbb{R}$, which is continuous and twice-differentiable on the interval $I$, the function $f$ is concave on $I$ if

$$
\begin{align*}
\forall{x\in\text{int}I}:f''(x)\lt0.
\end{align*}
$$

#### Application of Concavity

**Definition**: Given a real interval $I\subseteq\mathbb{R}$, a function $f:I\to\mathbb{R}$, which is continuous and twice-differentiable on $I$, and a real number $\alpha\in\int I$, we say that the real number $\alpha$ is a $\text{``point of inflection"}$ if there exists a positive real number $\delta\in\mathbb{R}$, such that $(\alpha-\delta,\alpha+\delta)\subseteq I$, and at least one of the conditions hold;

- case 1: $f|_{(\alpha-\delta, \alpha]}$ is convex and $f|_{[\alpha, \alpha+\delta)}$ is concave, or
- case 2: $f|_{(\alpha-\delta, \alpha]}$ is concave and $f|_{[\alpha, \alpha+\delta)}$ is convex.

**Remarks**: Informally, an inflection point is a point in which the property of a function switches from concave to convex or from convex to concave.