# Basic Concepts and Notations

## Alphabets

**Definition**: We say that an *alphabet* $V$ is a finite, non-empty set of symbols, where a symbol is any arbitrary glyph.

**Definition**: We say that an element of an alphabet $V$ is called a *letter*.

## Words

**Definition**: We say that a finite sequence of letters from $V$ is called a *word* over $V$. For any word $u$ over $V$, we denote the length of $u$ with $|u|$.

**Definition**: We denote the word with length zero using $\epsilon$, where $|\epsilon|=0$.

**Definition**: Given an alphabet $V$, we denote a set which contains every possible word over $V$, including the empty word, using $V^{*}$.

We also define the set of all words over $V$ except the empty word using $V^{+}$ where $V^{+}=V^{*}\setminus\{\epsilon\}$.

Additionally, we order words in $V^{*}$ in length-lexicographic order, where
- letters in $V$ are totally-ordered,
- shorter words appear before longer words, and
- two words of the same length are in lexicographic order.

### Operations on words

#### Word Concatenation

**Definition**: Given an alphabet $V=\{a_{1},\ldots,a_{n},b_{1},\ldots,b_{m}\}$ and two words $u=a_{1}\ldots a_{n}$ and $v=b_{1}\ldots b_{n}$, we define the concatenation between $u$ and $v$ as;

$$
\begin{align*}
uv :&= a_{1}\ldots a_{n}b_{1}\ldots b_{m}.
\end{align*}
$$

From this operation we have $|uv|=|u|+|v|$. For example; given $V=\{a,b\}$ and two words $u=aa$ and $v=bb$, we have $uv=aabb$.

**Theorem**: Word concatenation is associative. Given an alphabet $V$, we can prove that $\forall u,v,w\in V^{*}:u(vw)=(uv)w$.

**Theorem**: Word concatenation is non-commutative. Given an alphabet $V$, we can prove that $\exists u,v\in V^{*}:uv\ne vu$. 

**Theorem**: Given an alphabet $V$, the set of all words in $V^{*}$ is closed under word concatenation. That is, for any pair of words $u,v\in V^{*}$ their concatenations $uv$ and $vu$ are also words over $V$.

**Theorem**: Given an alphabet $V$, the empty word $\epsilon$ is the identity element of word concatenation operation. That is, for any word $u$ over  $V$, $u=u\epsilon=\epsilon u$ holds.

**Theorem**: Given an alphabet $V$, the word concatenation alongside $V^{*}$ is a semi-group with the empty word $\epsilon$ as the identity element.

#### Word Exponentiation

**Definition**: Let $n\in\mathbb{N}_{\ge0}$ and $V$ be an alphabet, we define the $n$th exponent of a word $u\in{V^{*}}$ as follows;
- $u^{0}:=\epsilon$, and 
- $u^{n}:=uu^{n-1}$ for $n\gt0$.

For example; let $V\in\{a,b\}$ and $u=ab$, we have;
- $u^{0}=\epsilon$,
- $u^{1}=ab$,
- $u^{2}=abab$, 
- $u^{3}=ababab$, etc.

**Theorem**: The product  rule of common exponent holds for word exponentiation operation. That is, given an alphabet $V$ and a word $u$ over $V$, we have $u^{n}u^{m}=u^{n+m}$ for $m,n\in\mathbb{N}_{\ge0}$.

#### Word Reversal

**Definition**: Given an alphabet $V$ and a word $u$ over $V$, we say that the reversal of $u$ is the letter sequence of $u$ in reversed order. We denote the reversal of $u$ with $u^{R}$.

For example; let $V=\{a,b,c,d,e\}$ and $u=abcde$, then we have $u^{R}=edcba$.

**Theorem**: We say that a word $u$ is a palindrome if $u=u^{R}$.

**Theorem**: Given an alphabet $V$, the properties of word reversal operation are;
- $\epsilon^{R}=\epsilon$,
- $(vu)^{R}=u^{R}v^{R}$ for any $u,v\in V^{*}$,
- $(u^{R})^{R}=u$ for any $u\in V^{*}$, and
- $(u^{n})^{R}=(u^{R})^{n}$ for any $u\in V^{*}$ and $n\in\mathbb{N}_{\ge0}$.