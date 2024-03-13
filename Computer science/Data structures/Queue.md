# Queue

**Definition**: A **Queue** is an ordered collection of elements. Elements in a queue are removed in the same order in which they are inserted, called **first-in-first-out**.

## Common operations

**Theorem**: The time complexity of **ENQUEUE** and **DEQUEUE** operations is $O(1)$.

**Theorem**: Indexing an element in a queue has $O(n)$ where $n$ is the size of the queue.

**Theorem**: The space complexities of a queue is $\Theta(n)$ are $O(n)$, where $n$ is the number of elements in a queue.

### ENQUENE operation

**Definition**: The **ENQUEUE** operation adds an element to the end of the queue.

Consider an empty queue "Q", enqueue three elements "A, B, and C" to it.

0. Initial queue:

	```mermaid
	flowchart RL
	Q.head-->NIL
	Q.tail-->NIL
	```

1. Prepare to enqueue "A":

	```mermaid
	flowchart RL
		Q.head & Q.tail-.->A
		Q.head & Q.tail-->NIL
		NIL ~~~ A
	```

1. Enqueued "A":

	```mermaid
	flowchart RL
		Q.head-->A
		Q.tail-->A
	```

1. Prepare to enqueue "B":

	```mermaid
	flowchart RL
		B-.->A
		Q.tail-.->B
		Q.tail-->A
		Q.head-->A
	```

1. Enqueued "B":

	```mermaid
	flowchart RL
		Q.tail-->B-->A
		Q.head-->A
	```

1. Prepare to enqueue "C":

	```mermaid
	flowchart RL
		C-.->B
		Q.tail-.->C
		Q.tail-->B-->A
		Q.head-->A
	```

1. Enqueued "C":

	```mermaid
	flowchart RL
		Q.head-->A
		Q.tail-->C-->B-->A
	```

### DEQUEUE operation

**Definition**: The **DEQUEUE** operation removes the first element from the queue.

Consider a queue "Q", dequeue three elements "A, B, and C" from it.

0. Initial queue:

	```mermaid
	flowchart RL
		Q.head-->A
		Q.tail-->C-->B-->A
	```

1. Prepare to dequeue "A":

	```mermaid
	flowchart RL
		Q.head-->A
		Q.head-.->B
		Q.tail-->C-->B-->A
	```
	
1. Dequeued "A":

	```mermaid
	flowchart RL
		Q.head-->B
		Q.tail-->C-->B
		B~~~A
	```

1. Prepare to dequeue "B":

	```mermaid
	flowchart RL
		Q.head-.->C
		Q.head-->B
		Q.tail-->C-->B
	```
	
1. Dequeued "B":

	```mermaid
	flowchart RL
		Q.head-->C
		Q.tail-->C
		C~~~B
	```

1. Prepare to dequeue "C":

	```mermaid
	flowchart RL
		Q.head & Q.tail-.->NIL
		Q.head & Q.tail-->C
		NIL~~~C
	```

1. Dequeued "C":

	```mermaid
	flowchart RL
		Q.head & Q.tail-->NIL
		NIL~~~C
	```