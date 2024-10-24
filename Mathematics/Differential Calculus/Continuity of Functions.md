# Continuity of Functions

## Introduction to Continuity of Functions

**Definition**: We define the ball neighborhood of a point $x_{0}\in\mathbb{R}$  with a radius $r\in(0,\infty)$ to be a set $B(x_{0}, r):=\{p\in\mathbb{R}\mid|p-x_{0}|\lt r\}$ or the interval $(x_{0}-r,x_{0}+r)$.

**Definition**: Given a function $f\in\mathbb{R}\to\mathbb{R}$ and a point $a\in\mathbb{D}_{f}$, we say that the function $f$ is continuous at $a$ if, and only if 

$$
\begin{align*}
\forall\epsilon\gt0 : \exists\delta\gt0 : \forall x\in B(a, \delta)\cap D_{f} : f(x)\in B(f(a),\epsilon).
\end{align*}
$$

From this definition, we can observe that if $a$ is also an accumulation point of $D_{f}$, then $\lim_\limits{x\to a} f(x)\to f(a)$.

**Definition**: We denote the set which contains every continuous function at point $a$ with $C(a)$.

**Definition**: Given a function $f\in\mathbb{R}\to\mathbb{R}$, we say that the function $f$ is continuous if it is continuous at every point in its domain. More formally, the function $f$ is said to be continuous if 

$$
\begin{align*}
\forall a\in D_{f} : f\in C(a).
\end{align*}
$$

We can observe that the following functions are continuous since they satisfy the above-mentioned definition; constant functions, identity functions, polynomials, rational functions (such as $x\to \frac{1}{x}$, and the analytical functions (such as $\sin, \cos, \tan$).

**Theorem**: (Transference  Theorem for Continuity)

$$
\begin{align*}
f\in C(a)\iff \forall x\in D_{f} : \lim x = a \implies \lim f(x)=\lim f(a)
\end{align*}.
$$

Informally, given two functions $f,g\in\mathbb{R}\to\mathbb{R}$ and a point $a\in D_{f}\cap D_{g}$ where $f,g\in C(a)$, operations between $f,g$ is also continuous. In other words, $f+g,f-g,f\cdot g, \frac{f}{g}\in C(a)$.  Even function composition, $g\in C(a)$ and $f\in C(g(a))$, then $f\circ g\in C(a)$.

### Discontinuity of Functions

**Definition**: Given a function $f\in\mathbb{R}\to\mathbb{R}$ and a point $a\in D_{f}$, we say that the function $f$ is *discontinuous* at $a$ if $f\notin C(a)$.

From this definition, we will have three classifications of discontinuous function at point $a$.

**Definition**: We say that a function $f$ has a *removable discontinuity* at $a$ if $f$ has a limit at $a$, but the limit is different from the image of $f$ at $a$. Formally,

$$
\exists\lim_\limits{a}f\land\left(\lim_\limits{a}f\ne f(a)\right).
$$

**Definition**: We say that a function $f$ has a *jump discontinuity*  at $a$ if $f$ has left-hand and right-hand sides limits at $a$, but the limits are different. Formally;

$$
\exists\lim_\limits{a-}f\land\exists\lim_\limits{a+}f\land\left(\lim_\limits{a-} f\ne\lim_\limits{a+} f\right).
$$

**Definition**: We say that a function $f$ has a *second-kind discontinuity* at $a$ if the left-hand or right-hand side limit does not exist at point $a$. Formally,

$$
\nexists\lim_\limits{a-}f\lor\nexists\lim_\limits{a+}f.
$$

## Compact Sets

**Definition**: Given a non-empty set $H\subset\mathbb{R}$ and a point $x_{0}\in\mathbb{R}$, we say that $x_{0}$ is an *interior point* of $H$ if $\exists r\in(0,\infty) : B(x_{0}, r)\subseteq H$.

**Definition**: We say that $x_0$ is an *exterior point* of $H$ if $\exists r\in(0,+\infty) : B(x_{0}, r)\cap H = \emptyset$.

**Definition**: We say that $x_{0}$ is a *boundary point* of $H$ if $\forall r\in(0,+\infty) : B(x_0, r)\cap H \ne0\land B(x_0, r)\cap(\mathbb{R}\setminus H)\ne\emptyset$.

**Definition**: Given a non-empty set $H$, we denote the set containing all interior points of $H$ using $int H$. Formally,

$$
int H :=\{x\in\mathbb{R}\mid\exists r\in(0,+\infty) : B(x, r)\subset H\}.
$$

Similarly, we denote the set containing all exterior point of $H$ using $ext H$, and the set containing all boundary point of $H$ using $\partial H$.

**Definition**: Given a set $H\subseteq\mathbb{R}$, we say that $H$ is an *open set* if $\partial H\subseteq (\mathbb{R}\setminus H)$. However, if $\partial H\subseteq H$, then we say that $H$ is a *closed set*.

Informally, if $H$ does not contain any boundary point, intuitively, we say that $H$ is open, and $H$ is closed if it contains all of its boundary points.

**Theorem**: Given a non-empty set $H\subseteq\mathbb{R}$, the set $H$ is closed if, and only if

$$
\forall x_n\in H (n\in\mathbb{N}) : \lim_\limits{n\to\infty} x_n\in H.
$$

> [!warning]
> I do not know what the above theorem means.

**Definition**: Given a non-empty set $H\subseteq\mathbb{R}$, we say that the set $H$ is a *compact set* if for every sequence $x_n\in H (n\in\mathbb{N})$ there exists a subsequence $(x_{v_{n}})$  such that the subsequence $(x_{v_{n}})$ is convergent and $\lim_\limits{n\to+\infty} x_{v_n}\in H$.

**Theorem**: A non-empty set $H\subseteq\mathbb{R}$ is compact if, and only if, it is closed and bounded.

**Theorem**: A compact set $H\subseteq\mathbb{R}$ has minimal and maximal elements.