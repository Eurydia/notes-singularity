# SQL

## Introduction to SQL

### Common Data Types

In SQL, we commonly use the following data types;
- $\texttt{INTEGER}$ or $\texttt{INT}$, 
- $\texttt{REAL}$ or $\texttt{FLOAT}$,
- $\texttt{CHAR(n)}$: a fixed-length string of $n$ characters,
- $\texttt{VARCHAR(n)}$: a string of at most $n$ characters,
- $\texttt{DATE}$

### Boolean Expressions

 The common Boolean operators are;
 - $\texttt{AND}$
 - $\texttt{OR}$
 - $\texttt{NOT}$

Along with the well-known inequality operators. However, in SQL, we have three possible value for a Boolean expression, true, false, and null.

To demonstrate, we consider true to be one, false to be zero, and null to be $\frac{1}{2}$. We define the Boolean operators to be 
- $\texttt{AND}:=\min$
- $\texttt{OR}:=\max$
- $\texttt{NOT}(x):=1-x$

With these definition, we can see that the expression;

$$
\begin{align*}
\texttt{TRUE AND (FALSE OR (NOT NULL))} 
\end{align*}
$$

is equal to

$$
\begin{align*}
\min\left( 1, \max\left( 0, 1-\frac{1}{2} \right) \right)&=\min\left( 1,\max\left( 0, \frac{1}{2} \right) \right)\\
&=\min\left( 1, \frac{1}{2} \right)\\
&=\frac{1}{2},
\end{align*}
$$

so our original expression evaluates to null.

### Patterns

A pattern is useful when we are matching strings. It is a string literal with two wild cards;
- the percentage sign $\texttt{``\%''}$ matches any character any number of times
- the underscore symbol $\texttt{``\_''}$ matches any character once

For example, we can use patterns in conjunction with $\texttt{LIKE}$ and clause to create a Boolean expression;

$$
\begin{align*}
\texttt{<some string> LIKE 'aa\%'}
\end{align*}
$$

matches any string that starts with two a's.

## SQL Syntax

### Table Declaration

We can declare a table in many ways. The simplest has the following syntax

$$
\begin{align*}
\texttt{CREATE TABLE <name> (<column definition>);}
\end{align*}
$$

For example, the following table declaration

```sql
CREATE TABLE sells (
	bar CHAR(20),
	beer VARCHAR(20),
	price REAL
);
```

creates a table with the name $\text{``sells''}$ with three columns $\text{``bar'', ``beer'',}$ and $\text{``price.''}$

#### Non-nullable Columns

We can provide a constraint to a column definition, so that it cannot contain null value. We use the following syntax to provide the constraint;

$$
\begin{align*}
\texttt{<column name> <column data type> NOT NULL}
\end{align*}
$$

For example, 

```sql
CREATE TABLE sells (
	bar CHAR(20) NOT NULL,
	beer VARCHAR(20),
	price REAL
);
```

#### Assigning a Default Value to Columns

We can assign a default value to a column using the following syntax;

$$
\begin{align*}
\texttt{<column name> <column data type> DEFAULT <default value>}
\end{align*}
$$

For example, 

```sql
CREATE TABLE sells (
	bar CHAR(20),
	beer VARCHAR(20),
	price REAL DEFAULT 0.0
);
```

However, the default value should have the appropriate data type, and if the column is non-nullable, then the default value cannot be null. In other words, the following table declaration is invalid;


```SQL
CREATE TABLE sells (
	bar CHAR(20),
	beer VARCHAR(20) NOT NULL DEFAULT NULL,
	price REAL
)
```

### Table Deletion

We can remove a table from a database using the following syntax;

$$
\begin{align*}
\texttt{DROP TABLE <table name>;}
\end{align*}
$$

### Select-from-where Queries

Using a select-from-where query, we can select columns from a table with some conditions. For example, we can select the names of employees with certain amount of salary;

```SQL
SELECT name 
FROM Employee 
WHERE salary > 1500
```

Alternatively, we can select every column in the table using the star symbol $\texttt{``*''}$, rather than just selecting the name;

```sql
SELECT *
FROM Employee 
WHERE salary > 1500
```

#### Renaming Columns

We can rename a column to something else in our select-from-where query without modifying the underlying table using the $\texttt{``<column name> AS <new column name>''}$ syntax. For example, 

```sql
SELECT name AS employee name 
from Employee
```

#### Computed Columns

We can introduce a new column in our select-from-where query. For example, let's introduce a new column in our query, and we will compute this column by doubling the salary of an employee;

```sql
SELECT name, 2*salary
FROM Employee
```

The result of the query will have two columns, $\text{``name''}$ and $\text{``2*salary''}$. That is, we use the expression itself as the column name. We can change it by [[#Renaming Columns|renaming]] the column;


```sql
SELECT name, 2*salary AS doubled salary
FROM Employee
```

The result of the query will be $\text{``name''}$ and $\text{``doubled salary''}$ instead.

We can also use constants in rather than a expression.

```sql
SELECT 'hi' as Hi, name
From Employee
```

#### Complex Condition

