# Background and notation

## Imaginary unit

**Definition**: $i$ is a solution to the equation $x^{2}=-1$, called the **imaginary unit**.

## Complex number

### Algebraic form

**Definition**: The expression of the form $a+bi$, where $a,b\in\mathbb{R}$ and $i$ is the imaginary unit, is called a **complex number**, more specifically, the **algebraic form** of a complex number.

This form is also referred to as the **cartesian form** or the **rectangular form**.

**Definition**: The complex numbers of the form $0+bi$ where $b\in\mathbb{R}$ and $i$ is the imaginary unit, are called **pure complex number**.

**Definition**: The **real part** of a complex number $a+bi$ is the real number $a\in\mathbb{R}$, denoted by $Re(a+bi)$.

**Definition**: The **imaginary part** of a complex number $a+bi$ is the real number $b\in\mathbb{R}$, denoted by $Im(a+bi)$.

**Definition**: Two complex numbers $a+bi, c+di$ are consider to be equal if:

$$
(a=c)\land(b=d).
$$

### Polar form

**Definition**: The complex number $a+bi$ can be written the form $r\cdot(\cos{\phi}+i\sin{\phi})$ where $r:=|a+bi|$ and $\phi$ is the angle between the real number axis and the vector $(a,b)$.

## Complex number set

**Definition**: The **complex number set** is the set $\mathbb{R}\times\mathbb{R}$ along with **addition** and **multiplication**, denoted by $\mathbb{C}$.

**Definition**: The **argument** of a complex number $z:=r(\cos\phi+i\sin\phi)\in\mathbb{C}$, denoted by $arg(z)$, is the angle $\phi\in[0,2\pi)$.

### Addition

**Definition**: **Addition** between two complex numbers is defined as:

$$
(a+bi)+(c+di) := (a+c)+(b+d)i.
$$

**Theorem**: Addition on $\mathbb{C}$ is **associative**:

$$
\forall a,b,c\in\mathbb{C} : (a+(b+c) = (a+b)+c).
$$

**Theorem**: Addition on $\mathbb{C}$ is **commutative**:

$$
\forall a,b\in\mathbb{C} : (a+b = b+a).
$$

**Theorem**: There exist a additive identity in $\mathbb{C}$, denoted by $0$:

$$
\forall a\in\mathbb{C} : (a+0=0+a=0).
$$

**Definition**: The **additive inverse** of a complex number is denoted by $-a$:

$$
\forall a\in\mathbb{C} : (a+(-a)=(-a)+a=0).
$$

**Theorem**: Addition is distributive over multiplication:

$$
\forall a,b,c\in\mathbb{C} : ((a+b)c = ac + bc).
$$

### Multiplication

**Definition**: Multiplication between two complex numbers is defined as:

$$
(a+bi)(c+di) := (ac-bd)+(ad+bc)i.
$$

**Theorem**: **Multiplication** on $\mathbb{C}$ is **associative**:

$$
\forall a,b,c\in\mathbb{C} : (a(bc) = (ab)c).
$$

**Theorem**: **Multiplication** on $\mathbb{C}$ is **commutative**:

$$
\forall a,b\in\mathbb{C} : (ab = ba).
$$

**Theorem**: The multiplication identity in $\mathbb{C}$ is denoted by $1$:

$$
\forall a\in\mathbb{C} : (a1=1a=a).
$$

**Definition**: The **multiplication inverse** of a complex number is denoted by $a^{-1}$:

$$
\forall a\in\mathbb{C}\setminus\{0\} : aa^{-1}=a^{-1}a=1.
$$

**Theorem**: Multiplication is distributive over Addition:

$$
\forall a,b,c\in\mathbb{C} : (a(b+c) = ac + bc).
$$

## Absolute value 

**Definition**: The absolute value of a complex number $a+bi$, denoted by $|z|$, is defined as:

$$
|a+bi| = \sqrt{a^{2}+b^{2}}.
$$

## Conjugate

**Definition**: The conjugate of a complex number $z:= a+bi$, denoted by $\overline{z}$, is defined as:

$$
\overline{z} := a-bi.
$$

**Theorem**: The sum of two complex conjugates is the complex conjugate of the sum:

$$
\forall a,b\in\mathbb{C} : (\overline{a}+\overline{b}=\overline{a+b}).
$$

**Theorem**: The product of two complex conjugates is the complex conjugate of the product:

$$
\forall a,b\in\mathbb{C} : (\overline{a}\cdot\overline{b}=\overline{a\cdot b}).
$$

**Theorem**: The sum of a complex number with its conjugate is twice its real part:

$$
\forall a\in\mathbb{C} : (a+\overline{a}=2Re(a)).
$$

**Theorem**: The difference of a complex number with its conjugate is twice its real part:

$$
\forall a\in\mathbb{C} : (a+\overline{a}=2Re(a)).
$$

**Theorem**: The product of a complex number with its conjugate is the square of the complex number:

$$
\forall a\in\mathbb{C} : (a\overline{a}=|a|^{2}).
$$

## Roots

**Definition**: The $n$-th root of a complex number $z$ are those complex numbers $w$ such that $w^{n}=z$.

**Theorem**: De Moivre’s formulas where $w:=|w|(\cos\alpha+i\sin\alpha)$ and $z:=|z|(\cos\beta+i\sin\beta)$:

$$
wz = |w||z|(\cos(\alpha+\beta) + i\sin(\alpha+\beta)).
$$

Similarly,

$$
zw^{-1} = \frac{|z|}{|w|}(\cos(\beta-\alpha) + i\sin(\beta-\alpha)).
$$

And for $n\in\mathbb{N}+$:

$$
z^{n} = |z|^{n}(\cos(n\beta) + i\sin(n\beta)).
$$

**Definition**: The $n$-th roots of one are called $n$-th **roots of unity**.
