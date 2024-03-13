# Stack

**Definition**: A **stack** is an ordered collection of elements. Elements of a stack are removed in the reserved order in which they are inserted, called **last-in-first-out**.

## Operations

### PUSH operation

**Definition**: The **PUSH** operation adds an element onto the top of the stack. **Pushing** an element onto a full stack results in an error called **stack overflow**.

Consider an empty stack "S" and push "A, B, and C" onto it.

0. Initial stack:

	```mermaid
	flowchart RL
	S.top-->NIL
	```

1. Prepare to push "A":

	```mermaid
	flowchart RL
	S.top-.->A-.->NIL
	S.top-->NIL
	```

1. Pushed "A":

	```mermaid
	flowchart RL
		S.top-->A-->NIL
	```

1. Prepare to push "B":

	```mermaid
	flowchart RL
		B-.->A
		S.top-.->B
		S.top-->A-->NIL
	```

1. Pushed "B":

	```mermaid
	flowchart RL
		S.top-->B-->A-->NIL
	```

1. Prepare to push "C":

	```mermaid
	flowchart RL
		C-.->B
		S.top-.->C
		S.top-->B-->A-->NIL
	```

1. Pushed "C":

	```mermaid
	flowchart RL
		S.top-->C-->B-->A-->NIL
	```

### POP operation

**Definition**: The **POP** operation removes the top-most element from the stack. **Popping** an element from an empty stack results in an error called **stack underflow**.

Consider a stack "S" with three elements "A, B, and C" and pop them from the it.

0. Initial stack:

	```mermaid
	flowchart RL
		S.top-->C-->B-->A-->NIL
	```

1. Prepare to pop "C":

	```mermaid
	flowchart RL
		S.top-.->B
		S.top-->C-->B-->A-->NIL
	```

2. Popped "C":

	```mermaid
	flowchart RL
		S.top-->B-->A-->NIL
	```

3. Prepare to pop "B":

	```mermaid
	flowchart RL
		S.top-.->A
		S.top-->B-->A-->NIL
	```

4. Popped "B":

	```mermaid
	flowchart RL
		S.top-->A-->NIL
	```

5. Prepare to pop "A":

	```mermaid
	flowchart RL
		S.top-.->NIL
		S.top-->A-->NIL
	```

6. Popped "A":

	```mermaid
	flowchart RL
	S.top-->NIL
	```
