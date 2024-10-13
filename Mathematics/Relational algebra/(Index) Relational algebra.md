# Relational algebra

Relational algebra is a framework consisting of operators and operands, where the operands are relations. We should note that relational algebra uses sets as its underlying structure. This means the result we produce using relational algebra will be inherently unique and unordered.

## Terminologies

### Relation

**Definitions**: A *relation* is a named, two-dimensional table in a database. We say that the column names of each table in the database are the *attributes*, and each row is a *tuple*.

**Definition**: A *relational schema* is an identifier along with a tuple containing attributes. We use it to define the name of a relation and its attributes. For example;

*Employee(name: string, department: integer)*

is a valid schema. We have an *Employee* relation with two attributes; the *name* which we represent with a string, and the *department* which we represent with an integer.

However, there are not strict convention for a relational schema. As such, the following is also valid;

*Employee(name, department)*

has omitted the data types for the attributes, but we can still understand the structure of the schema.

### Database

**Definition**: A *database* is a collection of one or more relations.

**Definition**: A *database schema* is a collection of all *relational schema* in a given database.

## Operators

### Usual set operators

Since the underlying structure for relational algebra is a set, we can perform the usual set operation given that the two relations have the same relational schema. 

Let $A,B$ be relations with the same relational schema where

$$
\begin{align*}
&A:=\begin{array}{|c|c|}
Bar & Beer & Price\\ 
\hline 
Joe’s & Bud & 2.50 \\
Joe’s & Miller & 2.75 \\ 
Sue’s & Bud & 2.50
\end{array}
& B:=\begin{array}{|c|c|}
Bar & Beer & Price\\ 
\hline 
Joe’s & Bud & 2.50\\
Jack’s & Bud & 2.75
\end{array}
\end{align*}
$$

The usual set operations behave in the following way;

- Set union;

$$
\begin{align*}
&A\cup B=\begin{array}{|c|c|}
Bar & Beer & Price\\ 
\hline 
Joe’s & Bud & 2.50 \\
Joe’s & Miller & 2.75 \\ 
Sue’s & Bud & 2.50\\
Jack’s & Bud & 2.75
\end{array}
\end{align*}
$$

- Set intersection;

$$
\begin{align*}
&A\cap B=\begin{array}{|c|c|}
Bar & Beer & Price\\ 
\hline 
Joe’s & Bud & 2.50 \\
\end{array}
\end{align*}
$$

- Set difference;

$$
\begin{align*}
&A\setminus B=\begin{array}{|c|c|}
Bar & Beer & Price\\ 
\hline 
Jack’s & Bud & 2.75
\end{array}
\end{align*}
$$

> [!notice] Intuition
> From these behaviors, we can deduce that two rows are equal if and only if they have the same relational schema, and every attribute is equal.

### Selection

**Definition**: Given a relation $R$, we use selection to select specific rows from $R$. We use $\sigma_{\mathcal{C}}$ to denote selection where $\mathcal{C}$ represents the Boolean condition.

Informally, $\sigma_{\mathcal{C}}$ filters rows in $R$. It keeps those rows which satisfy $\mathcal{C}$ and discards those that do not.

For example, let $A$ be a relation where

$$
\begin{align*}
&A=\begin{array}{|c|c|}
Bar & Beer & Price\\ 
\hline 
Joe’s & Bud & 2.50 \\
Joe’s & Miller & 2.75 \\ 
Sue’s & Bud & 2.50\\
\end{array}
\end{align*}
$$

We define a relation $B$ from $A$ as

$$
\begin{align*}
B=\sigma_{Bar=\text{``Joe's"}}(A)=\begin{array}{|c|c|}
Bar & Beer & Price\\ 
\hline 
Joe’s & Bud & 2.50 \\
Joe’s & Miller & 2.75 \\ 
\end{array}
\end{align*}
$$

Additionally, we define relation $C$ from $A$ as

$$
\begin{align*}
C=\sigma_{Price=2.75\land Bar=\text{``Joe's"}}(A)=\begin{array}{|c|c|}
Bar & Beer & Price\\ 
\hline 
Joe's & Miller & 2.75 \\ 
\end{array}
\end{align*}
$$

### Projection

**Definition**: Given a relation $R$, we use *projection* to create new relation with specific attributes from $R$. We use $\pi_{L}$ to denote projection, where $L$ is a list of attributes in $R$.

Informally, while selection acts as a filter function, projection is a mapping function. The order of attributes is the same as given in the project, from left to right.

For example, let $A$ be a relation where

$$
\begin{align*}
&A=\begin{array}{|c|c|}
Bar & Beer & Price\\ 
\hline 
Joe’s & Bud & 2.50 \\
Joe’s & Miller & 2.75 \\ 
Sue’s & Bud & 2.50\\
\end{array}
\end{align*}
$$

We define $B$ as a project of $A$;

$$
\begin{align*}
&B=\pi_{Bar,Price}(A)=\begin{array}{|c|c|}
Bar &  Price\\ 
\hline 
Joe’s & 2.50 \\
Joe’s & 2.75 \\ 
Sue’s & 2.50\\
\end{array}
\end{align*}
$$

In additional, we also allow an *extended projection* where $L$ can be any arbitrary expression. This allows us to include additional attributes which are present in the underlying relation.

For example, we can define $C$ as an extended projection of $A$

$$
\begin{align*}
&C=\pi_{Bar,Beer,Price,2\cdot Price\rightarrow DPrice}=\begin{array}{|c|c|c|}
Bar & Beer & Price & DPrice\\ 
\hline 
Joe’s & Bud & 2.50 & 5.00\\
Joe’s & Miller & 2.75 & 5.50 \\ 
Sue’s & Bud & 2.50 & 5.00\\
\end{array}
\end{align*}
$$

which has an additional attribute *DPrice* which we compute from doubling the *Price* attribute.

## Materials

- Relational algebra PowerPoint on Basic Operations and Relational Algebra on Bag Data Type: http://infolab.stanford.edu/~ullman/fcdb/aut07/slides/ra.pdf