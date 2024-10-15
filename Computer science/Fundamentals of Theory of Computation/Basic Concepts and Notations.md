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

**Theorem**: Word concatenation is non-commutative. Given an alphabet $V$, we can prove that $\exists u,v\in V^{*}:uv\ne vu$. We can observe that word concatenation operation is commutative only when $V$ contains a single letter.

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

#### Prefixes, Suffixes, and Sub-words

**Definition**: Given an alphabet $V$, and two words $u,v$ over $V$, we say that $u$ is a *sub-word* of $v$ when $\exists x,y\in V^{*}:v=xuy$. In addition to the previous condition, if $u\ne v$, we say that $u$ is a  *proper sub-word* of $v$.

**Definition**: Given an alphabet $V$ and two words $u,v$ over $V$, we say that $u$ is a *prefix* of $v$ if $\exists x\in V^{*}:v=ux$. If $u\ne v$, we say that $u$ is a *proper suffix* of $v$.

**Definition**: Similarly, given an alphabet $V$ and two words$u,v$ over $V$, we say that $u$ is a *suffix* of $v$ if $\exists x\in V^{*}:v=xu$. If$u\ne v$, we say that $u$ is a *proper suffix* of $v$.

## Languages

**Definition**: Given an alphabet $V$, we say that a subset $L$ of $V^{*}$ is a *language* over $V$.

**Definition**: If a language $L$ over $V$ contains infinitely many words, we say that $L$ is an infinite language, and if $L$ contains finitely many words, we say that $L$ is a finite language.

**Definition**:  We say that the empty subset of $V^{*}$ is the *empty language*, we denote this language with $\emptyset$.

### Operations on Language

#### Language Union, Intersection, and Difference 

Given an alphabet $V$ and two languages $L_{1},L_{2}$ over $V$, we cab perform the usual set operations on the languages. Informally, the union of languages, the intersection of languages, and the difference of languages behave in the same way as their set operation counterparts.

#### Language Complement

**Definition**: Given an alphabet $V$ and a language $L$ over $V$, we define the *complement language*  of $L$ as $\overline{L}:=V^{*}\setminus L$.

#### Language Concatenation

**Definition**: Given an alphabet $V$ and two languages $L_{1}, L_{2}$ over $V$, we define the concatenation of $L_{1},L_{2}$ as $L_{1}L_{2}:=\{u_{1}u_{2}|u_{1}\in L_{1}\land u_{2}\in L_{2}\}$.

For example, give $V=\{a,b\},L_{1}=\{ab,bb\},L_{2}=\{a,bba\}$, we have $L_{1}L_{2}=\{aab,abb,bab,bbb\}$.

**Theorem**: From the above-mentioned example, we can observe that language concatenation operation is associative, but non-commutative.

Given an alphabet $V$, we can also observe that $\forall L\in V^{*}:\{\epsilon\}L=L\{\epsilon\}=L$ holds.

**Theorem**: Given an alphabet $V$, the set containing languages over $V$ along with the language concatenation operation is a semi-group with an identity element $\{\epsilon\}$.

#### Language Exponentiation

**Definition**: Given an alphabet $V$, a non-negative integer $n\in\mathbb{N}_{\gt0}$, and a language $L$ over $V$, we define the exponentiation of $L$ as follows;
- $L^{0}:=\{\epsilon\}$, and
- $L^{n}:=LL^{n-1}$.

For example, given $V=\{a,b\}$ and $L=\{a,bb\}$, we have;
- $L^{0}=\{\epsilon\}$,
- $L^{1}=\{a,bb\}$,
- $L^{2}=LL=\{aa,abb,bba,bbbb\}$,
- $L^{3}=LL^{2}=\{aaa,aabb,abba,abbbb,bbaa,bbabb,bbbba,bbbbbb\}$, etc.

**Theorem**: Product rule of language exponentiation; given an alphabet $V$ and a language $L$ over $V$, we have

$$
\begin{align*}
L^{m}L^{n}=L^{m+n}.
\end{align*}
$$

#### Language Iterative Closure

**Definition**: Given an alphabet $V$ and a language $L$ over $V$, we define the *iterative closure* of $L$ as $L^{*}:=\bigcup_{i\ge0}L^{i}$. In addition, we say that $L^{+}:=\bigcup_{i\gt0}L^{i}$ is the *positive iterative closure* of $L$.

We can observe that $L^{+}=L^{*}$ when $\epsilon\in L$ and $L^{+}=L^{*}\setminus\{\epsilon\}$ when$\epsilon\notin L$.

#### Language Reversal

**Definition**: Given an alphabet $V$ and a language $L$ over $V$, we define the reversal of $L$ as $L^{R}:=\{u^{R}|u\in L\}$.

#### Language Prefix and Suffix Closure

**Definition**: Given an alphabet $V$ and a language $L$ over $V$, we define the *prefix closure* of $L$ to be 

$$
\begin{align*}
Pre(L):=\{u|u\in V^{*}\land \exists v\in V^{*}:uv\in L\}.
\end{align*}
$$

**Definition**: Similarly, we define the *suffix closure* of $L$ to be

$$
\begin{align*}
Suf(L):=\{u|u\in V^{*}\land\exists v\in V^{*}:vu\in L\}
\end{align*}
$$

### Properties of Language Operation

**Theorem**: Properties of language reversal operation; given an alphabet $V$ and a language $L$ over $V$, we have
- $(L^{R})^{R}=L$,
- $(L_{1}\ldots L_{n})^{R}=L_{n}^{R}\ldots L_{1}^{R}$,
- $(L^{n})^{R}=(L^{R})^{n}$ for $n\ge0$,
- $(L^{*})^{R}=(L^{R})^{*}$,
- $L^{*}L^{*}=L^{*}$,
- $(L^{*})^{*}=L^{*}$,
- $(L_{1}\cup L_{2})^{*}=(L_{1}^{*}L_{2}^{*})^{*}$, and
- $L_{1}(L_{2}\cup L_{3})=L_{1}L_{2}\cup L_{1}L_{3}$.

### Word Homomorphism

**Theorem**: Given two alphabets $V_{1},V_{2}$, we say that a mapping $h:V_{1}^{*}\to V_{2}^{*}$ is a *word homomorphism* if it satisfies the following;
- for every word $u\in V^{*}_{1}$, there exists only one word $v\in V^{*}_{2}$ such that $h(u)=v$, and
- $h(uv)=h(u)h(v)$ holds for any pair of words $u,v\in V^{*}_{1}$.

**Definition**: Given two  alphabets $V_{1},V_{2}$ and a word homomorphism $h:V^{*}_{1}\to V^{*}_{2}$, we say that $h$ is $\epsilon$-free if $\forall u\in V^{+}_{1}:h(u)\ne\epsilon$.

**Definition**: Given two  alphabets $V_{1},V_{2}$, a language $L$ over $V_{1}$, and a word homomorphism $h:V^{*}_{1}\to V^{*}_{2}$, we define the *homomorphic image* of $L$ by $h$ to be $h(L):=\{h(u)|u\in L\}$.

 We can observe that $h(L)\subseteq V^{*}_{2}$.