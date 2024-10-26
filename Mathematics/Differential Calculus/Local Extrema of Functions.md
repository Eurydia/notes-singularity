# Local Extrema of Functions

## Introduction to Local Extrema of Functions

**Definition**: Given a function $f\in\mathbb{R}\to\mathbb{R}$ and a point $a\in D_f$, we say that $f$ has a *local minimum* at $a$ if

$$
\exists r\in(0,+\infty) : \forall x\in B(a,r)\cap D_f : f(x)\ge f(a).
$$

**Definition**: Given a function $f\in\mathbb{R}\to\mathbb{R}$ and a point $a\in D_{f}$ , we say that $f$ has a *strict local minimum* at $a$ if there exists a small neighborhood around $a$ such that the image of those elements in the neighborhood, except $a$ itself, is strictly greater than the image of $a$;

$$\begin{align*}
\exists r\in(0,+\infty) : \forall x\in B(a,r)\setminus\{a\} : f(x)\gt f(a).
\end{align*}$$

Similarly, we say that a function $f$ has a *local maximum* at $a$ or a *strict local maximum* at $a$ in the same way.

**Theorem**: (First derivative test for local extremum) Give a function $f\in\mathbb{R}\to\mathbb{R}$ and a point $a\in D_f$ such that $f\in D(a)$ and $a$ is a local extremum of $f$, then $f'(a)=0$.

Informally, since the first derivative represents the change in slope of the original function. At a local extremum, the slope of the original function is zero.

## Mean-Value Theorems

**Theorem**: (Rolle's theorem) Given two points $a,b\in\mathbb{R}$ and a function $f:[a,b]\to\mathbb{R}$, where $f$ is continuous and everywhere-differentiable, such that $f(a)=f(b)$, then

$$\begin{align*}\exists\xi\in(a,b) : f'(\xi)=0.\end{align*}$$

**Theorem**: (Extended mean-value theorem or Cauchy's mean-value theorem) Given two real numbers $a,b\in\mathbb{R}$, which are the starting point and the terminal point of an interval, and two continuous, everywhere-differentiable functions $f,g:[a,b]\to\mathbb{R}$ such that $\forall x\in(a,b) : g'(x)\ne0$, then

$$\begin{align*}\exists\xi\in(a,b) : \frac{f(b)-f(a)}{g(b)-g(a)} = \frac{f'(\xi)}{g'(\xi)}. \end{align*}$$

**Theorem**: (Lagrange's mean-value theorem) Given two points $a,b\in\mathbb{R}$, which are the starting point and the terminal point of a interval, and a continuous, everywhere-differentiable function $f:[a,b]\to\mathbb{R}$, then 

$$\begin{align*}\exists\xi\in(a,b): \frac{f(b)-f(a)}{b-a} =f'(\xi).\end{align*}$$

## Discussion of Monotonicity

We can discuss about the monotonicity of a function by looking at its first-order derivative.

**Theorem**: (First derivative test for monotonicity) Given an interval $I\subseteq\mathbb{R}$ (the type of $I$ is irrelevant to this theorem) and a continuous, everywhere-differentiable function $f:I\to\mathbb{R}$, then
- $f$ is a strictly increasing function if $\forall x\in \text{int}I : f'(x)\gt0$ 
- $f$ is a strictly decreasing function if $\forall x\in\text{int}I : f'(x)\lt0$
- $f$ is a constant function if $\forall x\in\text{int}I : f'(x)=0$

## Inverse Trigonometric Functions

**Theorem**: There exists a unique number $\alpha\in(0,2)$ such that $\cos\alpha=0$.

**Definition**: We define $\pi:=2\alpha$ where $\cos\alpha=0$.

**Definition**: We define the inverse of the sine function to be 

$$\begin{align*}
\arcsin&:[-1,1]\to\left[ -\frac{\pi}{2}, \frac{\pi}{2} \right],\\
\arcsin&:=\left(\sin\mid_{\left[ -\frac{\pi}{2}, \frac{\pi}{2} \right]}\right)^{-1}.
\end{align*}$$

**Definition**: We define the inverse of the cosine function to be 

$$\begin{align*}
\arccos&:[-1,1]\to[0,\pi],\\
\arccos&:=\left(\cos|_{[0,\pi]}\right)^{-1}.
\end{align*}$$

**Definition**: We define the inverse of the tangent function to be 

$$\begin{align*}
\arctan&: \mathbb{R}\to\left( -\frac{\pi}{2}, \frac{\pi}{2} \right),\\
\arctan&:=\left(\tan\mid_{\left( -\frac{\pi}{2}, \frac{\pi}{2} \right)}\right)^{-1}.
\end{align*}$$

**Definition**:  We define the inverse of the cotangent function to be

$$\begin{align*}
\text{arccot}&:\mathbb{R}\to(0,\pi),\\
\text{arccot} &:= \left(\cot\mid_{(0,\pi)}\right)^{-1}.
\end{align*}$$

### Derivatives of the Inverse of Trigonometric Functions

Next, we will discuss about the derivatives of the inverse trigonometric functions.

Given an interval $I:=\left( -\frac{\pi}{2}, \frac{\pi}{2} \right)$ and a function $f:(-1,1)\to\mathbb{{R}}:=\sin x, f^{-1}(y):=\arcsin y$, we apply the theorem of derivative inverse of functions;

$$\begin{align*}\arcsin'y&=(f^-1)'(y)\\
&=\frac{1}{\sin'(\arcsin y)}\\
&=\frac{1}{\cos(\arcsin y)}.
\end{align*}$$

From the definition of $\arcsin$ mentioned above, we know that $\arcsin y\in\left( -\frac{\pi}{2}, \frac{\pi}{2} \right)$, we can observe that $\cos(\arcsin y)\gt0$, which means we can proceed.

Next we apply the Pythagorean theorem;

$$\begin{align*}
\arcsin'(y)&=\frac{1}{\cos(\arcsin y)}\\
&=\frac{1}{\sqrt{1-(\sin(\arcsin y))^2}}
\end{align*}$$

We recognize that $\sin(\arcsin y)$ is the same structure as $f(f^{-1}(y))$ which is equivalent to $y$ itself, so we have

$$\begin{align*}
\arcsin'(y)&=\frac{1}{\sqrt{1-(\sin(\arcsin y))^2}}\\
&=\frac{1}{\sqrt{1-y^2}}.
\end{align*}$$


We can obtain the first-order derivative of $\arccos$ in a similar manner to $\arcsin$. For $y\in(-1,1)$, we have

$$\begin{align*}
\arccos'(y)=-\frac{1}{\sqrt{1-y^2}}.
\end{align*}$$