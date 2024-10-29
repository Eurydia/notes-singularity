# Antiderivatives

**Remarks**: The antiderivative could be thought of as the opposite process of differentiation. In a sense, if we were given the first-order derivative of a function, we can discuss about the original function using antiderivatives. More commonly, we refer to this process as indefinite integration.

## Introduction to Antiderivatives

**Definition**: Given an open interval $I\in\mathbb{R}$, and two functions $f, F:I\to\mathbb{R}$, we say that the function $F$ is an $\text{``antiderivative of }f\text{"}$ if $F$ is differentiable on $I$ and 

$$
\begin{align*}
\forall{x\in I}: F'(x)=f(x).
\end{align*}
$$

**Theorem**: Given a real open interval $I\subseteq\mathbb{R}$ and two functions $f, F:I\to\mathbb{R}$ such that $F$ is an antiderivative of $f$, then the set of all antiderivative of $f$ is the set

$$
\begin{align*}
\{x\mapsto F(x)+C\mid C\in\mathbb{R}, x\in I\}.
\end{align*}
$$

**Definition**: Given a real open interval $I\subseteq\mathbb{R}$ and a functions $f:I\to\mathbb{R}$, we say that the set of all antiderivative of $f$ is the $\text{``indefinite intergral of }f\text{"}$, and we denote it by $\int{f}$ or $\int f(x)dx$.


**Theorem**: (Existence of antiderivative of a function) Given a real, open interval $I\subseteq\mathbb{R}$ and a function $f:I\to\mathbb{R}$, which is continuous on $I$, then the function $f$ has an antiderivative.

## Simple Integration Rules

**Theorem**: (Addition rule of integration) Given a real, open interval $I\subseteq\mathbb{R}$, and two functions $f,g:I\to\mathbb{R}$ such that both $f,g$ have antiderivatives, then $f+g$ also has an antiderivative. More formally,

$$
\begin{align*}
\int{f(x)+g(x)}dx=\int{f(x)}dx+\int{g(x)dx}.
\end{align*}
$$

**Theorem**: (Scalar multiplication rule of integration) Given a real, open interval $I\subseteq\mathbb{R}$, a function $f:I\to\mathbb{R}$, and a real number $\alpha\in\mathbb{R}$, if the function $f$ has an antiderivative, then $\alpha f$ also has an antiderivative. More formally,

$$
\begin{align*}
\int{\alpha\cdot f(x)dx}=\alpha\cdot\int{f(x)dx}.
\end{align*}
$$

**Theorem**: (Linear substitution rule of integration) Given a real, open interval $I\subseteq\mathbb{R}$, two functions $f,F:I\to\mathbb{R}$ such that $F$ is an antiderivative of $f$, two real numbers $a,b\in\mathbb{R}$ such that $a\ne0$ and a set $J:=\{x\in\mathbb{R}\mid ax+b\in I\}$, then $J$ is an open interval and 

$$
\begin{align*}
\forall{x\in J}:\int{f(ax+b)dx}=\frac{F(ax+b)}{a}.
\end{align*}
$$

**Theorem**: (Integrals of type $f^{(n)}\cdot f'$) Given a real, open interval $I\subseteq\mathbb{R}$ and a function $f:I\to\mathbb{R}$, which is continuous on $I$, and a real number $\alpha\in\mathbb{R}$ such that $(f(x))^{\alpha}$ exists for all $x\in I$, then

$$
\begin{align*}
\forall x\in I :\int{(f(x))^{\alpha}\cdot f'(x)}dx = 
\begin{cases*}
\frac{(f(x))^{\alpha+1}}{\alpha+1} & if $\alpha\ne-1$\\
\int{\frac{f'(x)}{f(x)}dx}=\ln|f(x)| & if $\alpha=-1$
\end{cases*}
\end{align*}
$$

## Integrations of Rational Functions

**Remarks**: First, we recall that a rational function is a quotient of two polynomials. In this section, we will discuss a few integrations on the different rational functions.

**Theorem**: Given two real numbers $A,\alpha\in\mathbb{R}$, a positive integer $k\in\mathbb{Z}_{\gt0}$, and a real, open interval $I$, which can either be $(-\infty,\alpha)$ or $(\alpha,+\infty)$, if we consider the rational function 

$$
\begin{align*}
R&:I\to\mathbb{R},\\
R(x)&:=\frac{A}{(x-a)^{k}}.
\end{align*}
$$

The indefinite integral of the rational function $R$ is 

$$
\begin{align*}
\int{R(x)dx}=
\begin{cases*}
\frac{A\cdot(x-\alpha)^{-k+1}}{-k+1} & if $k\ge2$\\
A\cdot\ln|x-a| & if $k=1$
\end{cases*}
\end{align*}
$$

**Theorem**: Given real numbers $B,C,\beta,\gamma\in\mathbb{R}$ such that $\beta^{2}-4\gamma\lt0$, if we consider the rational function

$$
\begin{align*}
R&:\mathbb{R}\to\mathbb{R},\\
R(x)&:=\frac{Bx+C}{x^{2}+\beta x+\gamma}.
\end{align*}
$$

The indefinite integral of the rational function $R$ is

$$
\begin{align*}
\int{R(x)dx} = \frac{4}{4\gamma-\beta^{2}}\cdot \frac{1}{1+\left( \frac{2}{\sqrt{4\gamma-\beta^{2}}}x+\frac{\beta}{\sqrt{4\gamma-\beta^{2}}} \right)^{2}}.
\end{align*}
$$

**Theorem**: Given real numbers $B,C,\beta,\gamma\in\mathbb{R}$ such that $\beta^{2}-4\gamma\lt0$, a natural number $k\in\mathbb{N}$ such that $k\ge2$, if we consider the rational function

$$
\begin{align*}
R&:\mathbb{R}\to\mathbb{R},\\
R(x)&:=\frac{Bx+C}{(x^{2}+\beta x + \gamma)^{k}}.
\end{align*}
$$

The indefinite integral of the rational function $R$ can reduce down to form in the previous theorem.

**Theorem**: There exists real numbers $B_{1},C_{1},D_{1}\in\mathbb{R}$ such that

$$
\begin{align*}
\int{\frac{Bx+C}{(x^{2}+\beta x+\gamma)^{k}}dx} =\int{\frac{B_{1}x+C_{1}}{(x^{2}+\beta x+\gamma)^{k-1}}dx} + \int{\frac{D_{1}}{(x^{2}+\beta x+\gamma)^{k-1}}dx}.
\end{align*}
$$
%%
**Theorem**: Given two non-zero, real polynomials $P,Q$ such that the root factor form of $Q$ over $\mathbb{R}$ is

$$
\begin{align*}
Q(x)=(x-\alpha_{1})^{m_{1}}\cdot\ldots\cdot(x-\alpha_{r})^{m_{r}}\cdot(x^{2}+\beta_{1}x+\gamma_{1})^{n_{1}}\cdot\ldots\cdot(x^{2}+\beta_{s}x+\gamma_{s})^{n_{s}}.
\end{align*}
$$

If we consider the rational function 

$$
\begin{align*}
R(x):=\frac{P(x)}{Q(x)},
\end{align*}
$$

then the indefinite integral of the rational function $R$ is

$$
\begin{align*}
R(x)=\frac{P(x)}{Q(x)}=
\end{align*}
$$%%