# Euler's Totient and RSA

## Reduced Residue System

**Definition**: Given a positive natural number $m\in\mathbb{N^{+}}$, and a set $\mathbb{Z}_{m}$ containing all residue classes of $m$, we define the set of all invertible elements of $\mathbb{Z}_{m}$ to be; 

$$
\begin{align*}
\{\overline{a}\in\mathbb{Z}_{m}\mid\gcd(a,m)=1\}.
\end{align*}
$$

We denote this set using $\mathbb{Z}_{m}^{*}$.

**Example**: Consider $m=10$, then we have $\mathbb{Z}_{10}^{*}=\{\overline{1},\overline{3},\overline{7},\overline{9}\}$ since 1, 3, 7, and 9 are coprime with 10 and are invertible.

**Remarks**: If $m$ is a prime number, we can observer that $\mathbb{Z}_{m}^{*}$ contains all except the zero element in $\mathbb{Z}_{m}$.

**Theorem**: Given a positive natural number $m\in\mathbb{N}^{+}$ and a set $\mathbb{Z}_{m}$ containing all residue classes of $m$, then;

$$
\begin{align*}
\forall{a,b\in \mathbb{Z}_{m}^{*}}:\overline{a}\cdot\overline{b}\in\mathbb{Z}_{m}^{*}\land \frac{\overline{a}}{\overline{b}}\in\mathbb{Z}_{m}^{*}.
\end{align*}
$$

**Definition**: Given a positive natural number $m\in\mathbb{N}_{\gt0}$ and a set $\mathbb{Z}_{m}$ containing residue classes of $m$, we say that a set of integers containing exactly one element from each residue class $\overline{a}\in\mathbb{Z}_{m}^{*}$ is a reduced residue system modulo $m$.

**Remarks**: Consider $m=10$, we have infinitely many reduced residue system modulo ten, for example, $\{1,3,7,9\}$ and $\{11,13,17,19\}$.

## Euler's Totient Function

**Definition**: We define Euler's totient function $\phi$ to be a $\mathbb{N}_{\gt0}\to\mathbb{N}$ function where $\phi(n)$ is the number of integers between zero and $n-1$ that are coprime with $n$. Formally, we define $\phi$ as;

$$
\begin{align*}
\phi(n)=|\{k\in\mathbb{Z}\mid 0\le k\le n-1\land\gcd(n,k)=1\}|
\end{align*}.
$$

**Remarks**: Using this function, we can easily discuss the number of elements in a reduced residue system modulo $m$ simply using the function since $|\mathbb{Z}_{m}^{*}|=\phi(m)$.

**Theorem**: Given a positive natural number $n\in\mathbb{N}_{\gt0}$  such that $n\ge2$, the value of $\phi(n)$ is at most $n-1$;

$$
\begin{align*}
\forall{n\in\mathbb{N}_{\gt0}}:n\ge2\implies\phi(n)\le n-1.
\end{align*}
$$

**Theorem**: By definition of $\gcd$, then;

 $$
\begin{align*}
\phi(1)=1.
\end{align*}
$$

**Theorem**: Given a positive natural number $p\in\mathbb{Z}_{\gt0}$ such that $p$ is a prime number, then;

$$
\begin{align*}
\phi(p)=p-1.
\end{align*}
$$

**Theorem**: Given a positive natural number $p\in\mathbb{Z}_{\gt0}$ such that $p$ is a prime number, then;

$$
\begin{align*}
\phi(p^{k})&=p^{k}-p^{k-1}\\
&=(p-1)p^{k-1}.
\end{align*}
$$

**Theorem**: Given two positive natural numbers $a,b\in\mathbb{Z}_{\gt0}$ such that $a,b$ are coprime, then;

$$
\begin{align*}
\phi(a\cdot b)&=\phi(a)\cdot\phi(b).
\end{align*}
$$

**Remarks**:

**Theorem**: Given a positive natural number $n\in\mathbb{Z}_{\gt0}$ such that $n$ has the following canonically representation $p_{1}^{n_{1}}\ldots p_{k}^{n_{k}}$, then;

$$
\begin{align*}
\phi(n)=(p_{1}^{n_{1}}-p_{1}^{n_{1}-1})\cdot\ldots\cdot(p_{k}^{n_{k}}-p_{k}^{n_{k}-1}).
\end{align*}
$$

## Generalized Modular Exponentiation

**Theorem**: (Euler's totient theorem) Given a positive natural number $m\in\mathbb{N}_{\gt0}$ and an integer $a\in\mathbb{Z}$ such that $\gcd(a,m)=1$, then;

$$
\begin{align*}
a^{\phi(m)}\equiv 1\mod m.
\end{align*}
$$

The theorem also extends to reduced residue classes modulo $m$. That is;

$$
\begin{align*}
\forall{\overline{a}\in\mathbb{Z}_{m}^{*}} :\overline{a}^{\phi(m)}\equiv 1\mod m.
\end{align*}
$$

**Remarks**: Euler's totient theorem is particularly useful when optimizing modular exponentiation. Consider $137^{75}\equiv n\mod 10$, we make the observation that;

$$
\begin{align*}
137^{75}=7^{75}\mod 10.
\end{align*}
$$

Still, $7^{75}$ is computationally intensive, so simplify it further by applying Euler's totient theorem. First, we have $\phi(10)=4$, then we make an observation that

$$
\begin{align*}
7^{75}\equiv7^{4\cdot18+3}\equiv 7^{4\cdot18}\cdot7^{3}\mod 10.
\end{align*}
$$

By Euler's totient theorem, we simplify $7^{4\cdot18}\equiv1\mod 10$, so 

$$
\begin{align*}
1^{4\cdot18}\cdot7^{3}\equiv7^{3}\mod 10.
\end{align*}
$$

At this point, we can quickly compute $7^{3}\mod 10


## The RSA Algorithm

**Remarks**: RSA is an asymmetric encryption algorithm, so have two keys; a public key for encryption and  a private key for decryption.

The RSA algorithm relies on the fact that modern computers take an exponentially long time to perform prime factorization on large numbers. Let's consider two large prime numbers $p,q$, modern computes can quickly compute their product. The reversed is not true, given $n=pq$, without knowledge of $p,q$, performing prime factorization on $n$ can take so long that it is practically impossible.

We need to pick two prime numbers $p,q$ which are sufficiently large (~4000 digits in length) to ensure a secure encryption and decryption.

### RSA Encryption and Decryption

To encrypt a message using RSA, we need to convert our message into an integer. This integer $m$ will be our plain text representation. We encrypt $m$ by performing modular exponentiation;

$$
\begin{align*}
c\equiv m^{e}\mod p\cdot q.
\end{align*}
$$

The integer $c$ is our encrypted message and the exponent $e$ is the public exponent. We can freely share $p\cdot q$ and $e$.

We can decrypt a message $c$ by performing modular  exponentiation;

$$
\begin{align*}
m=c^{d}\mod p\cdot q.
\end{align*}
$$

The exponent $d$ is the private exponent, so we should keep it as a secret.

**Remarks**: From the encryption and decryption process, we can observe that;

$$
\begin{align*}
m\equiv c^{d}\equiv (m^{d})^{e}\equiv m^{de}\mod p\cdot q.
\end{align*}
$$

That is, by applying Euler's totient theorem, we can obtain the private exponent $d$ since the public exponent $e$ and modulus $p\cdot q$ are not secrets.

$$
\begin{align*}
m^{de}\equiv m^{ed\mod \phi(p\cdot q)}\mod p\cdot q.
\end{align*}
$$

We simply need to find the exponent $e$ such that $de\equiv1\mod \phi(p\cdot q)$ holds. In practice, however, we do not the values of $p,q$, we only know their product, so even if the RSA algorithm in vulnerable to such attacks in theory, it is not the case in practice. As we have mentioned during the introduction, it takes an astronomically long time to perform prime factorization on large numbers.

### Digital Signature

In RSA, anyone can send an encrypted message using the public key, but on the owner of the private key can decrypt it. We can reversed this process and obtain a digital signature.

By encrypting a message using the private key, anyone with a public key can decrypt this message. This is another useful application of RSA since receivers can be certain that the message they received came from the right sender.  

### Chinese Reminder Theorem

We can choose the public exponent $e$ to improve encryption speed. In most cases, we also need a way to quickly decrypt a message. 

Rather than computing $c^{d}\equiv m\mod p\cdot q$, we can compute the exponent in two parts; $m_{p}\equiv c^{d}\mod p$ and $m_{q}\equiv c^{d}\mod q$, then combine the result using Chinese reminder theorem.

First, we pre-compute three values before decryption

$$
\begin{align*}
d_{p}&\coloneqq d\mod p-1\\
d_{q}&\coloneqq d\mod q-1\\
v&\coloneqq q^{-1}\mod p.

\end{align*}
$$

We use these pre-computed  values to improve the efficiency of our decryption process by computing the $m_{p},m_{q}$ as follows;

$$
\begin{align*}
m_{p}&\coloneqq c^{d_{p}}\mod p\\
m_{q}&\coloneqq c^{d_{q}}\mod q.
\end{align*}
$$

We apply Chinese reminder theorem to obtain $m$ from $m_{p},m_{q}$;

$$
\begin{align*}
m_{d}&\coloneqq q^{-1}(m_{p}-m_{q})\mod p\\
m&=m_{q}+m_{d}q.
\end{align*}
$$

Normally, we can freely share the ordered pair $(e, p\cdot q)$ and keep the ordered pair $(d, p\cdot q)$ as a secret, but with this modification to improve the speed of decryption process, we often keep a 5-tuple instead $(p,q,d_{p},d_{q},q^{-1})$.

### Primality Tests