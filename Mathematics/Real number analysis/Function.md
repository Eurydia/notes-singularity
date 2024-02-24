# Function

A binary relation $f\subseteq A\times B$ is said to be a **function** if every element $x\in A$ is related to, at most, one element in $B$.

It is worth noting that; the underlying sets $A,B$ are called the **domain** and **codomain** of $f$, denoted by $dom(f)$ and $codom(f)$, respectively. They are different from **preimage** and **image** of $f$. The **preimage** of $f$ can be thought of as a subset of **domain**, which contains all **valid** input of $f$, and the image of $f$ is a subset of **codomain**.

At the time of writing, there is no widely-accepted notation for **preimage** and **image**.

Consider a binary relation $g\subseteq\mathbb{R}\times\mathbb{R}$ defined as $g:=\{(x,y)\in\mathbb{R}\times\mathbb{R} : y=\sqrt{x}\}$. The binary relation $g$ is a **function** since a real number $x\ge0$ relates only to one real number $y$. Although the **domain** and **codomain** of $g$ are defined as $\mathbb{R}$, the **preimage** and **image** of $g$ are $\mathbb{R}_{\ge0}$. 

It is entirely possible to define a binary relation in such a way that its **domain** is equal to its **preimage**. A binary relation $f\subseteq X\times Y$ whose **domain** is equal to its **preimage** can be denoted by $f:X\to Y$ instead.

## Components of a function

A function is defined based on three components; (1) its domain and codomain, (2) its preimage, and (3) its law of correspondence, or its function body.

## Restricting a function

Consider a function $f\subseteq A\times B$ and a set $H$ which is a subset of the preimage of $f$. The function $g\subseteq H\times B$ is a restriction of $f$,

$$g:=\{(x,f(x))\in A\times B: x\in H\}$$

The function $g\subseteq H\times B$ is denoted by $f_{|H}$.

## Injective function

A function $f\subseteq A\times B$ is said to be  **one-to-one** or **injective** if every elements $x$ in the preimage of $f$ relates to exactly one element $y$ in the image.

More formally, if preimage and image of $f$ are denoted as $\text{preimg}(f)\subseteq A$ and $\text{img}(f)\subseteq B$, respectively, then 

$$\forall x,x'\in\text{preimg}(f) : x\ne x'\implies f(x)\ne f(x').$$

## Inverse of a function

Consider an **injective** function $f\subseteq A\times B$, the inverse function of $f$, denoted by $f^{-1}\subseteq B\times A$, is defined as:

$$
f^{-1} := \{(f(x),x)\in B\times A: x\in\text{preimg}(f)\}.
$$

Intuitively, an inverse of a function **undoes** the effects of its counterpart. Thus $f^{-1}(f(x))=x$ for every $x\in\text{preimg}(f)$.

## Composing functions

At its core, a **function composition** refers to the process of applying two functions in succession.
Consider two functions $g\subseteq A\times B, f\subseteq X\times Y$, they can be composed in two ways. Either $g$ is applied first, then $f$, or $f$ is applied first, then $g$.

If $g$ is applied to some input $a\in\text{preimg}(g)$, then $f$, denoted $(f\circ g)(a)$, is pronounced as $f$ composition $g$. And if $f$ is applied first to some input $x\in\text{preimg}(f)$, then $g$, denoted by $(g\circ f)(x)$.

For the sake of simplicity, consider the first case $(f\circ g)(a)$. The composition is only valid if $g(a)\in\text{preimg}(f)$. In other words, the output of the first function must be in the preimage of the second function.

More formally, the functions $f\subseteq X\times Y, g\subseteq A\times B$ create the function composition $f\circ g$ defined as

$$f\circ g:=\{(a,y)\in A\times Y : \exists (x,y)\in X\times Y : g(a) = x\}$$