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

**Theorem**: (Scalar multiplication rule of integration) Given a real, open interval $I\subseteq\mathbb{R}$