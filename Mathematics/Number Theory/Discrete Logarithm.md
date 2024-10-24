# Discrete Logarithm

Built upon:
- [[Modular Arithmetic]]

## Prime Modulus

**Definition**: Given a prime number $p$ and  $\mathbb{Z}_{p}$, we denote the set of those elements in $\mathbb{Z}_{p}$ which do not contain $\overline{0}$ with $\mathbb{Z}^{*}_{p}$, or more formally;

$$
\begin{align*}
\mathbb{Z}_{p}^{*}:=\mathbb{Z}_{p}\setminus\{\overline{0}\}.
\end{align*}
$$

For example, take $p=5$, we have $\mathbb{Z}_{5}=\{\overline{0},\overline{1},\overline{2},\overline{3},\overline{4}\}$ and $\mathbb{Z}_{5}^{*}=\{\overline{1},\overline{2},\overline{3},\overline{4}\}$. 

In this example, we can observe that for a prime number $p$, $\mathbb{Z}_{p}^{*}$ contains $p-1$ elements.

**Theorem**: If $p$ is prime, then 

$$
\begin{align*}
\forall \overline{a},\overline{b}\in\mathbb{Z}_{p}^{*}:\left(\overline{a}\cdot\overline{b}\in\mathbb{Z}_{p}^{*}\right)\land\left(\frac{\overline{a}}{\overline{b}}\in\mathbb{Z}_{p}^{*}\right).
\end{align*}
$$

Informally, since $\mathbb{Z}_{p}^{*}$ does not contain the zero element, we can perform multiplication and division in $\mathbb{Z}_{p}^{*}$, however, the same is not true for addition and subtraction.

## Modular Exponentiation

The familiar exponentiation, where the exponent is a positive integer, is simply the repeated multiplication of the base. For example $5^{3}:=5\cdot5\cdot5$. Modular exponentiation operates under the same intuition. Take $p=7$ and $\mathbb{Z}_{7}$, we have $(\overline{5})^{3}:=\overline{5}\cdot\overline{5}\cdot\overline{5}=\overline{4}\cdot\overline{5}=\overline{6}$.

**Definition**: Given a positive integer $m\in\mathbb{N}_{\gt0}$, a partition $\overline{a}\in\mathbb{Z}_{m}$, and an integer $k\in\mathbb{Z}$, we define modular exponentiation to be

$$
\begin{align*}
(\overline{a})^{k}:=\begin{cases*}
\prod\limits_{1}^{k}\overline{a} & if $k\gt0$.\\
\overline{1} & if $k=1$.\\
\prod\limits_{1}^{-k}(\overline{a})^{-1} & if $k\lt0$ and $\overline{a}$ is invertible.\\
\end{cases*}
\end{align*}
$$

**Theorem**: If $a\equiv b\mod m$, then $a^{k}\equiv b^{k}\mod m$. 

Informally, this theorem ensures that whichever element we choose in  a class, the result of modular exponentiation remains consistent. For example; take $p=7$ and $\mathbb{Z}_{7}$, we can see that $5^{3}\equiv 12^{3}\mod7$, so in modular exponentiation, we be certain that $(\overline{5})^{3}$ will be the same as $(\overline{12})^{3}$. In other words, the element we chose to represent the class has no affect on the calculation.

**Definition**: The order of an element $\overline{a}\in\mathbb{Z}_{m}$ is the smallest $k\in\mathbb{N}_{\gt0}$ where $(\overline{a})^{k}=\overline{1}$. We denote the order of an element $\overline{a}$ in $\mathbb{Z}_{m}$ with $o(\overline{a})$.

For example, take $p=7$, the order of $\overline{4}$ is three.

**Theorem**: (Fermat's little theorem) If $p$ is a prime and $a\in\mathbb{Z}$ and $p\nmid a$, then $a^{p-1}\equiv 1\mod p$.

This theorem applies to residue classes in our case; $\forall \overline{a}\in\mathbb{Z}^{*}_{p}:(\overline{a})^{p-1}=\overline{1}$. In other words, the order of an element can be, at most, $p-1$.

**Theorem**: (Lagrange's theorem) If $p$ is a prime and $\overline{a}\in\mathbb{Z}^{*}_{p}$, then $o(\overline{a})\mid p-1$.

## Fast Exponentiation

By definition of exponentiation, given an positive integer exponent $n$ and a base $a$, we have to perform $n-1$ multiplications. For example; $a^{4}=a\cdot a\cdot a\cdot a$, however, in this case, we can perform the exponentiation in only two multiplication; $(a^{2})^{2}$ is *technically* two multiplications rather than three.

The effect is more pronounced with larger exponents, for example;

$$
\begin{align*}
a^{22} &= (a^{11})^{2}\\
&= (a^{10}\cdot a)^{2}\\
&= ((a^{5})^{2}\cdot a)^{2}\\
&= ((a^{4}\cdot a)^{2}\cdot a)^{2}\\
&= (((a^{2})^{2}\cdot a)^{2}\cdot a)^{2}.
\end{align*}
$$

In the demonstration above, rather than computing the exponentiation in  21 multiplications, we used only 6 multiplication. We define a more general approach to be

$$
\begin{align*}
a^{n}=\begin{cases*}
(a^{\frac{n}{2}})^{2} & if $n$ is even.\\
a^{n-1}\cdot a & if $n$ is odd.
\end{cases*}
\end{align*}
$$

We keep applying these rules until every term in $a^{n}$ is either in the form of $a^{2}$ or $a$.

## Discrete Logarithm

**Definition**: Given a prime number $p$, we say that an element $\overline{g}\in\mathbb{Z}^{*}_{p}$ is a generator in $\mathbb{Z}_{p}^{*}$ if $o(\overline{g})=p-1$.

**Theorem**: If $\overline{g}$ is a generator in $\mathbb{Z}_{p}^{*}$, then $\forall\overline{a}\in\mathbb{Z}^{*}_{p} : \exists k\in\mathbb{N}:(\overline{g})^{k}=\overline{a}$.

Informally, by exponentiating a generator $\overline{g}\in\mathbb{Z}_{p}^{*}$, we can generate every element in $\mathbb{Z}_{p}^{*}$.

**Theorem**: If $p$ is a prime, then there exists at least one generator in $\mathbb{Z}_{p}^{*}$.

**Definition**: Given $p$ and $\overline{a},\overline{b}\in\mathbb{Z}^{*}_{p}$, we say the the smallest $x\in\mathbb{N}_{\ge0}$ for which $(\overline{b})^{x}=\overline{a}$ is the discrete logarithm of $\overline{a}$ to the base $\overline{b}$. We denote this equality with $x=\log_{\overline{b}}\overline{a}$.

For example, take $p=7$, the discrete logarithm of $\overline{6}$ to the base $\overline{5}$ is three since $(\overline{5})^{3} =\overline{6}$. In practice, we may choose to compute every power of $\overline{g}$ from $0$ to $p-2$, but this approach will not work when $p$ is large. 

Instead, we have a more efficient method called baby-step, giant-step algorithm. For this algorithm, we pick a number $N$ such that $N^{2}\approx p-1$, and express the discrete logarithm as some $x$ as $\overline{a}=(\overline{g})^{x}$. To apply the algorithm, we express $x=iN+j$ where $0\le i,j\lt N$, and we start the baby-step part of the algorithm, in which we compute the first power of $\overline{g}$: $\overline{1},\overline{g},(\overline{g})^{2},\ldots,(\overline{g})^{N-1}$. Then we start the giant-step part of the algorithm by repeatedly multiplying $\overline{a}$ with $(\overline{g})^{-N}$: $\overline{a},\overline{a}(\overline{g})^{-N},\overline{a}(\overline{g})^{-2N},\ldots$. The point at which these the baby-step and the giant step meet, in other words when $\overline{a}(\overline{g})^{-iN}=(\overline{g})^{j}$, is the point solution for $x$.