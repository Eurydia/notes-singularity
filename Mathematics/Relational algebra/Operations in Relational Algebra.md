# Operations in Relational Algebra

## Introduction to Relational Algebra Operations

**Definitions**: Given a two natural numbers $m,n\in\mathbb{N}\gt0$, we define 

$$
\begin{align*}
\text{``a relation $S$ with $m$ rows and $n$ columns''}
\end{align*}
$$

to be

$$
\begin{align*}
S\coloneqq\{(s_{j1},\ldots,s_{jn})\mid j=1,2,\ldots,m \}.
\end{align*}
$$

**Remarks**: Semantically, the each tuple represents a row in a table and each component of the tuple represents each column.

**Definition**: We say that a $\text{``relation schema"}$ is an ordered tuple which contains the column names and data types. For example, consider the following relation schema

$$
\begin{align*}
\text{(name: string, department: integer)},
\end{align*}
$$

in this example, the relation has two columns; we label the first column as $\text{``name''}$ and the second column as $\text{``department''}$. The first column contains strings and the second column contains integers.

**Remarks**: With these definitions, we are modelling a database into a mathematical object.

## Operations on Relations

**Remarks**: The well-known set operations, such as set union, set intersection, and set difference, only operable on relations which share the same relation schema. That is, the relations must share the same column names as well as the datatype.

### Selection

**Definition**: Given a relation $R$, we define the selection operation to be a unary operator with one parameter. We use the expression

$$
\begin{align*}
\text{``$\sigma_{\mathcal{c}}(R)$''}
\end{align*}
$$

to denote the selection of the relation $R$ under the Boolean expression $\mathcal{c}$. By evaluating the above-mentioned expression, we obtain those tuples in relation $R$ which satisfy the condition $\mathcal{c}$.

**Remarks**: Informally, we are looking at each row in $R$ one by one, and test each row against the condition $\mathcal{c}$. We also allow conditions in $\mathcal{c}$ to reference the column name in $R$. 

For example, let's consider a relation $A$ with the relation schema

$$
\begin{align*}
(\text{Bar:String}, \text{Beer:String}, \text{Price:Number})
\end{align*}
$$

We can perform an elementary selection by referencing one of the columns;

$$
\begin{align*}
\sigma_{\text{Bar=``Joe's''}}(A),
\end{align*}
$$

which selects only those rows whose $\text{``Bar''}$ column is $\text{``Joe's''}$.

We can also perform a more complex selection by referencing multiple columns;

$$
\begin{align*}
\sigma_{\text{Price=2.75$\land$Bar=``Joe's''}}(A),
\end{align*}
$$

which selects only those rows whose $\text{``Price''}$ column is exactly 2.75 and $\text{``Bar''}$ column is $\text{``Joe's''}$

### Projection

**Definition**: Given a relation $R$, we define the project operation to be a unary operator with one parameter. We use the expression

$$
\begin{align*}
\pi_{\mathcal{L}}(R),
\end{align*}
$$

where $\mathcal{L}$ is an ordered list of column names from relation schema of $R$. Semantically, we pick only those columns which are included in the $\mathcal{L}$. If the project causes duplicate rows, we remove all but one row.

**Remarks**: Let's consider a relation $A$ with the following relation schema

$$
\begin{align*}
\text{(Bar: String, Beer: String, Price: Number)},
\end{align*}
$$

we can rearrange the column order using the expression

$$
\begin{align*}
\pi_{\text{Price, Beer, Bar}}(A).
\end{align*}
$$

We can also remove one of the columns 

$$
\begin{align*}
\pi_{\text{Bar, Price}}(A).
\end{align*}
$$

#### Extended Projection

**Remarks**: Using projection, we cannot introduce a new column into the relation schema, which is not useful for us, but we define the extended projection operation.

**Definition**: Given a relation $R$, we define the $\text{``extended projection''}$ operation to be a unary operator with one parameter. We use the expression

$$
\begin{align*}
\pi_{\text{$\mathcal{K}$}}(R)
\end{align*}
$$

where $\mathcal{K}$ is an ordered tuple of arbitrary expression. If we want to introduce a new column, we must use the expression of the form

$$
\begin{align*}
\text{<Value>}\rightarrow\text{<Column name>}.
\end{align*}
$$

Let's consider a relation $A$ with relation schema 

$$
\begin{align*}
\text{(Bar:  String, Beer: String, Price: Number)}.
\end{align*}
$$

We can maintain the original columns and introduce a new column. We call the new column $\text{``DPrice''}$ which we obtain from doubling the original $\text{``Price''}$ column;

$$
\begin{align*}
\pi_{\text{Bar, Beer, Price, $2\cdot$Price$\rightarrow$DPrice}}(R).
\end{align*}
$$

### Cartesian Product

**Definition**: Given two relations $A,B$, we define the $\text{``cartesian product''}$ to be a binary operation. We denote the operation with

$$
\begin{align*}
A\times B.
\end{align*}
$$

Semantically, we take one row in $A$ and, one by one, we concatenate every row in $B$ to the end. If two columns have the same name, we rename those columns into $A.\text{name}$ and $A.\text{name}$.

### Theta Join

**Definition**: Given two relations $A,B$, we define $\text{``theta-join''}$ to be a binary operator with one parameter. We denote it using 

$$
\begin{align*}
A\bowtie_{\mathcal{c}}B
\end{align*}
$$

where $\mathcal{c}$ is a Boolean expression. Semantically, this operation applies the cartesian product then to the result we apply selection;

$$
\begin{align*}
A\bowtie_{\mathcal{c}}B = \sigma_{\mathcal{c}}(A\times B).
\end{align*}
$$

Much like selection, the expression $\mathcal{c}$ can reference column names in either relations.

### Natural Join

**Definition**: Given two relations $A,B$, we define $\text{``natural join''}$ to be a binary operation. We write them as

$$
\begin{align*}
A\bowtie B.
\end{align*}
$$

#### Natural Join on One Common Column

Let's consider two relations $X,Y$.

We define the relation $X$ to be the following table;

| Bar   | Beer   | Price |
| ----- | ------ | ----- |
| Joe's | Miller | 2.75  |

We define the relation $Y$ to be the following table;

| Bar   | Address   |
| ----- | --------- |
| Joe's | Maple st. |
| Joe's | River rd. | 

We obtain the following table if we apply natural join on $X$ and $Y$;

| Bar   | Beer | Price | Address   |
| ----- | ---- | ----- | --------- |
| Joe's | Bud  | 2.5   | Maple st. |
| Joe's | Bud  | 2.5   | River rd. | 

### Renaming

**Definition**: Given a relation $R$ which has $n\in\mathbb{N}_{\gt0}$ columns, we define the rename operator to be unary operator with one parameter. We write it as

$$
\begin{align*}
\rho_{a_{1},\ldots,a_{n}}(R).
\end{align*}
$$

Semantically, we rename the $i$th column of $R$ to $a_{i}$. 

## Materials

- Relational algebra PowerPoint on Basic Operations and Relational Algebra on Bag Data Type: http://infolab.stanford.edu/~ullman/fcdb/aut07/slides/ra.pdf.