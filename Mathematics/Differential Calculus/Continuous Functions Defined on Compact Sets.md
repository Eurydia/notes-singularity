# Continuous Functions Defined on Compact Sets

**Theorem**: Given a continuous function $f\in\mathbb{R}\to\mathbb{R}$ where $D_{f}$ is compact, the image of $f$ is also compact.

**Definition**: Given a function $f\in\mathbb{R}\to\mathbb{R}$, we define the minimum element of $f$ to be the minimum element in the image set of $f$, if one exists;

$$
\min f:=\min \{f(x)\mid x\in D_{f}\}.
$$

**Definition**: Similarly, we define the maximum element of $f$ to be the maximum element in the image set of $f$, if one exists;

$$
\max f:=\max\{f(x)\mid x\in D_{f}\}.
$$

**Theorem**: (Theorem of Weierstrass) If a function $f\in\mathbb{R}\to\mathbb{R}$ is continuous and $D_{f}$ is compact, then $f$ has minimum and maximum elements.

**Definition**: Given a function $f\in\mathbb{R}\to\mathbb{R}$, we say that $f$ is *uniformly continuous* if it is continuous at every point it its domain;

$$
\forall\epsilon\gt(0,+\infty) : \exists\delta\in(0,+\infty) : \forall x,y\in D_f : |x-y|\lt\delta\implies|f(x)-f(y)|\lt\epsilon.
$$

We can observe that every uniformly continuous function is a continuous function, but a continuous function is not necessarily a uniformly continuous function. Additionally, while the definition of a continuous function depends on a point on the domain and a radius, the definition of a uniformly continuous function depends on the radius.

One such example we can give where the function is continuous but not uniformly continuous is the function $f:(0,+\infty)\to\mathbb{R}$ defined as; 

$$f(x)\mapsto \frac{1}{x}.$$

**Theorem**: (Theorem of Heine on uniform continuity) If a function $f\in\mathbb{R}\to\mathbb{R}$ is continuous and $D_f$ is compact, then $f$ is uniformly continuous.

**Definition**: Given a function $f\in\mathbb{R}\to\mathbb{R}$ and a non-empty set $H\subseteq D_f$, we say that $f$ is *uniformly continuous on $H$* if the restriction of $f\mid_H$ is uniformly continuous.

## Continuous Functions  Defined on Intervals

**Theorem**: (Intermediate value theorem) Given a continuous function $f:[a,b]\to\mathbb{R}$, suppose that $f(a)\ne f(b)$, then

$$
\forall c\in (f(a),f(b)) : \exists\xi\in(a,b) : f(\xi)=c.
$$

**Theorem**: Given a  continuous function $f\in\mathbb{R}\to\mathbb{R}$ where $D_{f}$ is an interval, then the image set of $f$ is also an interval.

## Monotone and Continuous Functions  Defined on Intervals

**Theorem**: Given an interval $I\subseteq\mathbb{R}$ with $a$ as the starting point of $I$ and $b$ as the terminal point of $I$ and a continuous and monotone increasing function $f:I\to\mathbb{R}$, then the starting point of the image interval of $f$ is $\lim_\limits{a+}f$. Similarly, the terminal point of the image interval of $f$ is $\lim_\limits{b-}f$.

**Theorem**: Given an interval $I\subseteq\mathbb{R}$ and a continuous and injective function $f:I\to\mathbb{R}$, then $f$ is a monotone function.

## The Real Exponential and Logarithm Functions

**Theorem**: The function $\exp:\mathbb{R}\to\mathbb{R}$ is a strictly monotonically increasing function.

**Definition**: We define the inverse of the exponent function to be the natural logarithm function, denote by $\ln$. Formally,

$$
\ln:=(\exp)^{-1}. 
$$

From this definition, we can observe the following properties of $\ln$
1. $D_{\ln}=\text{codmn}(\exp)=(0,+\infty)$
2. $\text{codmn}(\ln)=D_{\exp}=\mathbb{R}$
3. $\ln1=0$
4. $\ln(xy)=\ln x + \ln y$

**Theorem**: The natural logarithm function is monotonically increasing.

**Theorem**: $\forall r\in\mathbb{Q} : \exp r = e^r$.

**Definition**: Given a real number $x\in\mathbb{R}$, we define $e^x$ to be $\exp x$.

**Definition**: Given two real numbers $x, a\in\mathbb{R}$ such that $a\gt0$, we define the exponential function with base $a$ to be $\exp_a(x):=\exp(x\cdot\ln a)$.

**Definition**: Given a real number $a\in\mathbb{R}$ such that $a\gt0$ and $a\ne1$, we define the inverse function of the exponential function with the base $a$ to be the logarithm function $\log_a:=(\exp_a)^{-1}$.