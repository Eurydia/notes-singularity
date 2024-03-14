# Linked list

**Definition**: In a linear linked list, a **sentinel element** is an element which does not have a reference to the next element.

## Linear singly linked list

**Definition**: A **linear singly linked list** is an ordered collection of element and each element has a reference to the next element.

For the sake of brevity, the term "linear singly linked" list will be shortened to "LSL".

```mermaid
flowchart LR
	L.head --> 1 --> 2 --> ... --> NIL
```

### Common operations

There are two common operations on LSL:
**INSERT** and **REMOVE**.

#### INSERT operation

**Definition**: The **INSERT** operation inserts an element at the head of an LSL. 

There are three ways an element can be inserted in an LSL. It can be inserted at the head, between elements or at the tail.


**INSERT** at head

Consider a LSL, the process of inserting an element "A" to its head:

0. Initial state:

	```mermaid
	flowchart LR
		L.head-->B-->C[...]-->NIL
	```

1. Prepare to insert "A":

	```mermaid
	flowchart LR
		L.head-->B-->C[...]-->NIL
		L.head-.->A-.->B
	```

1. Inserted "A":

	```mermaid
	flowchart LR
		L.head~~~B
		L.head-->A-->B-->C[...]-->NIL
	```

#### INSERT AFTER operation

**Definition**: The **INSERT AFTER** operation inserts an element into an LSL after a particular element, so this operation does not work on empty LSL.

Consider an non-empty LSL, insert an element "A" after the element "N":

0. Initial state:

	```mermaid
	flowchart LR
		L.head-->1[...]-->N-->2[...]-->NIL
	```

1. Prepare to insert "A":

	```mermaid
	flowchart LR
		L.head-->1[...]-->N-->2[...]-->NIL
		N-.->A-.->2
	```

1. Inserted "A":

	```mermaid
	flowchart LR
		N~~~2
		L.head-->1[...]-->N-->A-->2[...]-->NIL
	```

#### REMOVE HEAD operation

**Definition**: The **REMVOE HEAD** operation removes the first element from an LSL. Removing the head of an empty LSL causes it to **underflow**.

Consider a non-empty LSL, remove the first element from it:

0. Initial LSL:

	```mermaid
	flowchart LR
		L.head-->A-->B-->C[...]-->NIL
	```

1. Prepare to remove "A":

	```mermaid
	flowchart LR
		L.head-->A-->B-->C[...]-->NIL
		L.head-.->B
	```

1. Removed "A":

	```mermaid
	flowchart LR
		L.head~~~A
		L.head-->B-->C[...]-->NIL
	```

#### REMOVE AFTER operation

**Definition**: The **REMOVE AFTER** operation removes an element from an LSL which appears after a specific element. Removing an element from an empty LSL causes it to **underflow**.

Consider a non-empty LSL, the process of removing an element "A" which is preceded by "N" goes as follows:

0. Initial state of LSL:

	```mermaid
	flowchart LR
		L.head-->1[...]-->N-->A-->2[...]-->NIL
	```

0. Prepare to remove "A":
	
	```mermaid
	flowchart LR
		N-.->2
		L.head-->1[...]-->N-->A-->2[...]-->NIL
	```

0. Removed "A":

	```mermaid
	flowchart LR
		L.head-->1[...]-->N-->2[...]-->NIL
		N~~~A~~~2
	```

## Circular singly linked list

**Definition**: A **circular singly linked list** is a singly linked list whose last element element references the first element instead of NIL.

The term "circular singly linked list" is abbreviated to "CSL."

```mermaid
flowchart LR
	L.head --> 1["L[0]"]-->2["L[1]"]-->3[...]-->4["L[n]"] 
	4 --> 1
```

### Operations

There are four common operations on CSL: ****

## Linear doubly linked list

**Definition**: A **linear doubly linked list** is collection of ordered elements. Each element contains references to the previous and the next element.

```mermaid
flowchart LR
L.head --> 1["L[0]"]<-->2["L[1]"]<--> 3[...]-->4[NIL]
1-->0[NIL]
```

## Circular doubly linked list

**Definition**: A **circular doubly linked list** is a linear doubly linked list whose elements form a closed loop.

```mermaid
flowchart LR
	L.head --> 1["L[0]"]<-->2["L[1]"]<--> 3[...]<-->4["L[n]"]
	4<-->1
```
