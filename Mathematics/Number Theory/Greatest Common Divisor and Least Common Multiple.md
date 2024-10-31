# Greatest Common Divisor and Least Common Multiple

## Introduction to Greatest Common Divisor and Least Common Multiple

**Definition**: Given two integers $a,b\in\mathbb{Z}$ and a natural number $c\in\mathbb{N}$, we say that $c$ is the *greatest common divisor of $a,b$* if

$$
\begin{align*}
c\mid a\land c\mid b\land\forall{d\in\mathbb{N}}:d\mid a\land d\mid b\implies d\mid c,
\end{align*}
$$

and we use the notation $\gcd(a,b)$ to denote the greatest common divisor of $a,b$.

**Definition**: Given two integers $a,b\in\mathbb{Z}$ and a natural number $c\in\mathbb{N}$, we say that $c$ is the *least common multiple of $a,b$* if

$$
\begin{align*}
a\mid c\land b\mid c\land\forall{d\in\mathbb{N}}:a\mid d\land b\mid d\implies c\mid d,
\end{align*}
$$

and we use the notation $\text{lcm}(a,b)$ to denote the least common multiple of $a,b$.

**Theorem**: Given two natural numbers $a,b\in\mathbb{N}$, the product of their greatest common divisor and least common multiple is equal to the product of the original numbers;

$$
\begin{align*}
\forall{a,b\in\mathbb{N}}:\gcd(a,b)\cdot\text{lcm}(a,b)=a\cdot b.
\end{align*}
$$

### Properties of Greatest Common Divisor

**Theorem**: Given a natural number $a\in\mathbb{N}$, the greatest common divisor of $a$ is itself; ^c0206f

$$
\begin{align*}
\forall{a\in\mathbb{N}}: \gcd(a,a)=a.
\end{align*}
$$

**Theorem**: Given two integers $a,b\in\mathbb{Z}$, their greatest common divisor is commutative;

$$
\begin{align*}
\forall{a,b\in\mathbb{Z}}:\gcd(a,b)=\gcd(b,a).
\end{align*}
$$

**Theorem**: Given three integers $a,b,c\in\mathbb{Z}$, their greatest common divisor is associative;

$$
\begin{align*}
\forall{a,b,c\in\mathbb{Z}}:\gcd(a,\gcd(b,c))=\gcd(\gcd(a,b),c).
\end{align*}
$$

**Theorem**: Given a natural number $a\in\mathbb{N}$, the greatest common divisor of $a$ and zero is $a$;

$$
\begin{align*}
\forall{a\in\mathbb{N}}:\gcd(a,0)=\gcd(0,a)=a.
\end{align*}
$$

**Theorem**: Given two natural numbers $a,b\in\mathbb{N}$ such that $a\mid b$, the greatest common divisor between $a,b$ is $a$;

$$
\begin{align*}
\forall{a,b\in\mathbb{N}}:a\mid b\implies\gcd(a,b)=\gcd(b,a)=a.
\end{align*}
$$

**Theorem**: Given two integers $a,b\in\mathbb{Z}$ such that $a,b\lt0$, the greatest common divisor of $a,b$ is equal to the greatest common divisor of their absolute values;

$$
\begin{align*}
\forall{a,b\in\mathbb{Z}}:a\lt0\land b\lt0\implies\gcd(a,b)=\gcd(|a|,|b|).
\end{align*}
$$

**Theorem**: Given three natural numbers $a,b,m\in\mathbb{N}$, scalar multiplication is distributive over the greatest common divisor;

$$
\begin{align*}
\forall{a,b,m\in\mathbb{N}}:m\cdot\gcd(a,b)=\gcd(m\cdot a, m\cdot b).
\end{align*}
$$

**Theorem**: Given two positive natural numbers $a,b\in\mathbb{N}_{\gt0}$, their greatest common divisor of $a,b$ is inclusively between one and $\min(a,b)$;

$$
\begin{align*}
\forall{a,b\in\mathbb{N}_{\gt0}}:1\le\gcd(a,b)\le\min(a,b).
\end{align*}
$$

### Properties of Least Common Multiple

**Theorem**: Given a natural number $a\in\mathbb{N}$, the least common multiple of $a$ is itself;

$$
\begin{align*}
\forall{a\in\mathbb{N}}:\text{lcm}(a,a)=a.
\end{align*}
$$

**Theorem**: Given two integers $a,b\in\mathbb{Z}$, their least common multiple is commutative;

$$
\begin{align*}
\forall{a,b\in\mathbb{Z}}:\text{lcm}(a,b)=\text{lcm}(b,a).
\end{align*}
$$

**Theorem**: Given three integers $a,b,c\in\mathbb{Z}$, their least common multiple is associative;

$$
\begin{align*}
\forall{a,b,c\in\mathbb{Z}}:\text{lcm}(a,\text{lcm}(b,c))=\text{lcm}(\text{lcm}(a,b),c).
\end{align*}
$$

**Theorem**: Given a natural number $a\in\mathbb{N}$, the least common multiple of $a$ and zero is zero;

$$
\begin{align*}
\forall{a\in\mathbb{N}}:\text{lcm}(a,0)=0.
\end{align*}
$$

**Theorem**: Given two natural numbers $a,b\in\mathbb{N}$ such that $a\mid b$, the least common multiple of $a$ and $b$ is $b$;

$$
\begin{align*}
\forall{a,b\in\mathbb{N}}:a\mid b\implies\text{lcm}(a,b)=b.
\end{align*}
$$

**Theorem**: Given two negative integers $a,b\in\mathbb{Z}$, the least common multiple of $a$ and $b$ is equal to the least common multiple of their absolute values;

$$
\begin{align*}
\forall{a,b\in\mathbb{Z}}:a\lt0\land b\lt0\implies\text{lcm}(a,b)=\text{lcm}(|a|,|b|).
\end{align*}
$$

**Theorem**: Given three natural numbers $a,b,m\in\mathbb{N}$, scalar multiplication is distributive over the least common multiple;

$$
\begin{align*}
\forall{a,b,m\in\mathbb{N}}:m\cdot\text{lcm}(a,b)=\text{lcm}(m\cdot a, m\cdot b).
\end{align*}
$$

**Theorem**: Given two positive natural numbers $a,b\in\mathbb{N}_{\gt0}$, their least common multiple is inclusively between $\max(a,b)$ and $a\cdot b$;

$$
\begin{align*}
\forall{a,b\in\mathbb{N}_{\gt0}}:\max(a,b)\le\text{lcm}(a,b)\le a\cdot b.
\end{align*}
$$

## Coprimes

**Definition**: Given two integers $a,b\in\mathbb{Z}$, we say $a$ and $b$ are *coprime* if 

$$
\begin{align*}
\gcd(a,b)=1.
\end{align*}
$$

**Remarks**: In some special cases, we can determine the coprimality as follows;
- $\pm1$ are coprime with any number.
- Zero is coprime only with $\pm1$.

## Multi-argument Greatest Common Divisor and Least Common Multiple

**Remarks**: We can also define the behaviors of the greatest common divisor and least common multiple for more than two arguments.

**Definition**: Given a positive natural number $n\in\mathbb{N}_{\gt0}$ and $n$ integers $a_{1},\ldots,a_{n}\in\mathbb{Z}$, we define $n$-ary greatest common divisor to be;

$$
\begin{align*}
\gcd(a_{1},\ldots,a_{n}):=\gcd(a_{1},\gcd(a_{2},\gcd(\ldots,a_{n})\ldots)).
\end{align*}
$$

**Remarks**: For example, the ternary greatest common divisor of $10,12,16$, by definition, equal to 

$$
\begin{align*}
\gcd(10,12,16)&\overset{\text{def}}{=}\gcd(10,\gcd(12,16))\\
&=\gcd(10,4)\\
&=2.
\end{align*}
$$

**Definition**: Given a positive natural number $n\in\mathbb{N}_{\gt0}$ and $n$ integers $a_{1},\ldots,a_{n}\in\mathbb{Z}$, we define $n$-ary least common multiple to be

$$
\begin{align*}
\text{lcm}(a_{1},\ldots,a_{n}):=\text{lcm}(a_{1},\text{lcm}(a_{2},\text{lcm}(\ldots,a_{n})\ldots)).
\end{align*}
$$

**Definition**: Given a positive natural number $n\in\mathbb{N}_{\gt0}$ and $n$ integers $a_{1},\ldots,a_{n}\in\mathbb{Z}$, we say that $a_{1},\ldots,a_{n}$ are *coprime* if 

$$
\begin{align*}
\gcd(a_{1},\ldots,a_{n})=1.
\end{align*}
$$

**Definition**: Given a positive natural number $n\in\mathbb{N}_{\gt0}$ and $n$ integers $a_{1},\ldots,a_{n}\in\mathbb{Z}$, we say that $a_{1},\ldots,a_{n}$ are *pairwise coprime* if 

$$
\begin{align*}
\forall{i\in[1,n]}:\forall{j\in[1,n]}:i\ne j\implies\gcd(a_{i},a_{j})=1.
\end{align*}
$$

## Prime Factors Relation with Greatest Common Divisor and Least Common Multiple

**Theorem**: Given two integers $a,b\in\mathbb{Z}$, the prime factorization of $\gcd(a,b)$ is exactly those prime numbers, which are present in both the prime factorization of $a$ and $b$, with the smaller exponent.

**Theorem**: Given two integers $a,b\in\mathbb{Z}$, the prime factorization of $\text{lcm}(a,b)$ is exactly those prime numbers, which are present in either the prime factorization of $a$ or $b$, with the greater exponent.

**Remark**: For example, consider $120$ whose prime factorization is $2^{3}\cdot3\cdot5$ and $36$ whose prime factorization $2^{2}\cdot3^{2}$, we have

$$
\begin{align*}
\gcd(120, 36)&=2^{2}\cdot3\\
&=12.
\end{align*}
$$

Similarly, we have

$$
\begin{align*}
\text{lcm}(120,36)&=2^{3}\cdot3^{2}\cdot5\\
&=360.
\end{align*}
$$

**Remarks**: The above-mentioned theorems provide a faster way to compute the greatest common divisor and least common multiple of two numbers. However, we still need to know their prime factorizations. As such, obtaining the prime factorization of a large number becomes a challenge in and of itself.

### Euclidian Algorithm

**Remarks**: As discussed in the previous section, we need an efficient method of obtaining prime factorization of large numbers. The Euclidian algorithm provides a fast method of obtaining the greatest common divisor of two numbers.

**Theorem**: Given two integers $a,b\in\mathbb{Z}$, 

$$
\begin{align*}
\gcd(a,b)=\gcd(a+b,b)=\gcd(a-b,b)
\end{align*}
$$

holds.

**Definition**:  Given two integers $a,b\in\mathbb{Z}$, we recursively apply a theorem mention above repeatedly until we obtain the greatest common divisor of the form

$$
\begin{align*}
\gcd(c,c)=c.
\end{align*}
$$

For example, we will compute the greatest common divisor of $50$ and $22$. First, we apply the theorem which states that

$$
\begin{align*}
\gcd(50,22)=\gcd(50-22)=\gcd(28,22).
\end{align*}
$$

We will repeatedly the smaller number from the larger number until we can apply [[Greatest Common Divisor and Least Common Multiple#^c0206f|this theorem]]. 

$$
\begin{align*}
\gcd(28,22)&=\gcd(6,22)\\
&=\gcd(6,16)\\
&=\gcd(6,10)\\
&=\gcd(6,4)\\
&=\gcd(2,4)\\
&=\gcd(2,2)
\end{align*}
$$

At this point, we have $\gcd(2,2)$ and from [[Greatest Common Divisor and Least Common Multiple#^c0206f|this theorem]], we have

$$
\begin{align*}
\gcd(50,22)=\gcd(2,2)=2.
\end{align*}
$$

### Extended Euclidian Algorithm

**Theorem**: (Bezout's identity) Given two integers $a,b\in\mathbb{Z}$, there exists two integers $x,y\in\mathbb{Z}$ such that $ax+by=\gcd(a,b)$; ^878699

$$
\begin{align*}
\forall{a,b\in\mathbb{Z}}:\exists{x,y\in\mathbb{Z}}:ax+by=\gcd(a,b).
\end{align*}
$$

**Remarks**: Informally, we represent the greatest common divisor of two integers using their linear combination.

**Definition**: We say that the integers $x,y$ in the above-mentioned theorem are the *Bezout coefficient*  for $a$ and $b$.

**Definition**: Given two integers $a,b\in\mathbb{Z}$, we compute their Bezout coefficient using the extended Euclidean algorithm as follows.

To better demonstrate, let's consider $a=50$ and $b=22$. First, we rewrite $a,b$ to obtain the form

$$
\begin{align*}
r_{1}&=a&=50&=(1\cdot50)+(0\cdot22)\\
r_{2}&=b&=22&=(0\cdot50)+(1\cdot22).\\
\end{align*}
$$

In the next step, we compute $r_{3}=r_{1}-q\cdot r_{2}$, and we recall our above-mentioned example that the left-hand side of the equation is equal to six, so we have $q=\left\lfloor {\frac{r_{1}}{r_{2}}} \right\rfloor=2$;

$$
\begin{align*}
r_{3}=6&=r_{1}-2\cdot r_{2}\\
&=(1\cdot50+0\cdot22)-2\cdot(0\cdot50+1\cdot22)\\
&=(1\cdot50)-(2\cdot22).
\end{align*}
$$

And we repeatedly apply this process until the left-hand side of our equation reaches zero. For $r_{4}$, we have $q=\left\lfloor {\frac{r_{2}}{r_{3}}}\right\rfloor=3$;

$$
\begin{align*}
r_{4}=4&=r_{2}-3\cdot r_{3}\\
&=(0\cdot50)+(1\cdot22)-3\cdot(1\cdot50-2\cdot22)\\
&=(0\cdot50)+(1\cdot22)+(-3\cdot50)+(6\cdot22)\\
&=(-3\cdot50)+(7\cdot22).
\end{align*}
$$

For $r_{5}$, we have $q=\left\lfloor {\frac{r_{3}}{r_{4}}} \right\rfloor=1$ and the left-hand side is equal to $6\mod4=2$;

$$
\begin{align*}
r_{5}=2&=r_{3}-1\cdot r_{4}\\
&=(1\cdot50)+(-2\cdot22)-1\cdot((-3\cdot50)+(7\cdot22))\\
&=(1\cdot50)+(-2\cdot22)+(3\cdot50)+(-7\cdot22)\\
&=(4\cdot50)+(-9\cdot22)
\end{align*}
$$

Lastly, for $r_{6}$, we have $q=\left\lfloor {\frac{r_{4}}{r_{5}}} \right\rfloor=2$ and the left-hand side is $4\mod2=0$;

$$
\begin{align*}
r_{6}=0&=r_{4}-2\cdot r_{5}\\
&=(-3\cdot50)+(7\cdot22)-2\cdot((4\cdot50)+(-9\cdot22))\\
&=(-3\cdot50)+(7\cdot22)+(-8\cdot50)+(18\cdot22)\\
&=(-11\cdot50)+(25\cdot22).
\end{align*}
$$

However, since it took us six iterations to reduce the left-hand side of our equation down to zero, we consider only the coefficient of the second-to-last iteration, so we have

$$
\begin{align*}
r_{5}=2=(4\cdot50)+(-9\cdot22).
\end{align*}
$$

We can rearrange the equation to obtain the form given by [[Greatest Common Divisor and Least Common Multiple#^878699|Bezout's identity theorem]];

$$
\begin{align*}
(4a)+(-9b)=\gcd(50,22)=2.
\end{align*}
$$

Thus we obtain $x=4$ and $y=-9$ as the Bezout coefficient of $a$ and $b$.