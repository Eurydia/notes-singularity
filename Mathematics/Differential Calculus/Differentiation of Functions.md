# Differentiation of Functions

## Introduction to the Differentiation of Functions

**Definition**: Given a function $f\in\mathbb{R}\to\mathbb{R}$ and a point $a$ which is an interior point of $\text{dmn}(f)$, we say that $f$ is differentiable at $a$ if and only if

$$
\lim_\limits{x\to a}\left( \frac{f(x)-f(a)}{x-a} \right)\in\mathbb{R}.
$$

And we say that the number

$$
\lim_{a}\left( \frac{f(x)-f(a)}{x-a} \right)
$$

is the derivative of $f$ at $a$, denoted by $f'(a)$.

Alternatively, we may use $h:=x-a$ and obtain a different form;

$$
f'(a):=\lim_a\left( \frac{f(x)-f(a)}{x-a} \right)=\lim_\limits{h\to0}\left( \frac{f(a+h)-f(a)}{a} \right).
$$

This is useful in cases when we want to "free-up" $x$.

**Definition**: Given a point $a$, we denote the set containing every function which is differentiable at $a$ with $D(a)$.

**Definition**: Given a function $f\in\mathbb{R}\to\mathbb{R}$, if the set 

$$D_{f'}:=\{x\in\text{int} D_f\mid f\in D(x)\}$$

is not empty,  then the function 

$$f':D_{f'}\to\mathbb{R}$$

is the derivative function of $f$.

**Theorem**: Given a point $a$, if a function is differentiable at $a$, then $f$ is continuous at $a$;

$$f\in D(a)\implies f\in C(a).$$


## Derivatives of Well-known Functions

**Theorem**: The derivative of a constant function is zero;

$$f(x):=c, f'(x)=0$$

for some fixed $c\in\mathbb{R}$.

**Theorem**: The derivative of a linear function is the slope of the line;

$$f(x):=ax+b, f'(x)=a$$

for fixed $a,b\in\mathbb{R}$.

**Theorem**: The derivative of a power function is 

$$
f(x):=x^n, f'(x):=n\cdot x^{n-1}
$$

for fixed $n\in\mathbb{N}$.

**Theorem**: The derivative of the exponential function is itself;

$$
f(x):=e^x, f'(x):=e^x\cdot 1=e^x.
$$

**Theorem**: The derivative of the sine function is

$$
f(x):=\sin x, f'(x)=\cos x.
$$

**Theorem**: The derivative of the cosine function is

$$
f(x):=\cos x, f'(x):=\sin x.
$$

## Differentiation Rules

**Theorem**: Given a point $x$ and two functions $f,g$ such that $f,g$ are differentiable at $x$, then $f+g$ is differentiable at $x$ and

$$
(f+g)'(x) = f'(x)+g'(x).
$$

**Theorem**: Given a point $x$ and two functions $f,g$ such that $f,g$ are differentiable at $x$, then $fg$ is differentiable at $x$, and

$$
(fg)'(x)=f'(x)\cdot g(x) + f(x)\cdot g'(x).
$$

**Theorem**: Given a point $x$ and two functions $f,g$ such that $f,g$ are differentiable at $x$ and $g(x)\ne0$,  then $\frac{f}{g}$ is differentiable at $x$, and

$$
\left( \frac{f}{g} \right)'(x)=\left( \frac{f'(x)\cdot g(x) + f(x)\cdot g'(x)}{(g(x))^2} \right)
$$

**Theorem**: (Composition of derivative) Given a point $x$, and two functions $f,g\in\mathbb{R}\to\mathbb{R}$ such that $g\in D(x)$ and $f\in D(g(x))$, then 

$$(f\circ g)\in D(x)$$

and the derivative of the composition is

$$
(f\circ g)'(x)=f'(g(x))\cdot g'(x).
$$

**Theorem**: Given an open interval $I\subseteq\mathbb{R}$ and a monotonically increasing, everywhere-differentiable function $f:I\to\mathbb{R}$ such that $\forall x\in I : f'(x)\ne0$, then 

$$\forall y\in\text{codmn}(f) : f^{-1}\in D(y)$$

and  the derivative of $f$ is

$$
(f^{-1})'(y)=\left( \frac{1}{f'(f^{-1}(y))} \right).
$$

From these differentiation rules, we can obtain derivatives of basic more well-known functions.

**Theorem**: The derivative of the tangent function is

$$(\tan x)'=1+(\tan x)^2$$

by applying the quotient rule over the sine and cosine functions.

**Theorem**: The derivative of the natural logarithm function is

$$
(\ln(x))'=\frac{1}{x}
$$

by applying the inverse rule on the exponential function.



