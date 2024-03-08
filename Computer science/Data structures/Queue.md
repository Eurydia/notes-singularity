# Queue

**Definition**: A **Queue** is an ordered collection of elements. Elements in a queue are removed in the same order in which they are inserted, called **first-in-first-out**. In practice, a queue can be implemented as a specialized **array**.

A stack data structure can be represented with three attributes: queue size, head position, tail position, and an array or other data structure to store the data. 

**Definition**: The **ENQUEUE** operation adds an element to the end of the queue.

**Definition**: The **DEQUEUE** operation removes the first element from the queue.

The queue operations have $O(1)$ time complexity.

## Implementation

In TypeScript, a queue can be implemented with an array as follows:

```ts
type Queue {
	size: number;
	head: number;
	tail: number;
	data: number[];
}
```

The **head** and **tail** attributes are initialized to the same value at first.

```ts
const initQueue = (size: number): Queue => {
	return {
		size,
		head: 0,
		tail: 0,
		data: []
	};
}
```

A minimal **ENQUEUE** implementation adds an element to the **tail** of a queue, and increment itself. If needed **tail** can be reset and wrapped back around to the start of the array.

```ts
const enqueue = (q: Queue, element: number): void => {
	q.data[q.tail] = element;
	q.tail++;
	if (q.tail >= q.size) {
		q.tail = 0;
	}
} 
```

A minimal **DEQUEUE**