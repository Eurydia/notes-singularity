# Queue

**Definition**: A **Queue** is an ordered collection of elements. Elements in a queue are removed in the same order in which they are inserted, called **first-in-first-out**. In practice, a queue can be implemented as a specialized **array**.

A queue can be represented with four attributes: size, head position, tail position, and an array or other data structure to store the data. 



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

**Definition**: The **ENQUEUE** operation adds an element to the end of the queue.

```ts
const enqueue = (q: Queue, element: number): void => {
	q.data[q.tail] = element;
	q.tail++;
	if (q.tail >= q.size) {
		q.tail = 0;
	}
} 
```

**Definition**: The **DEQUEUE** operation removes the first element from the queue.

```ts
const dequeue = (q: Queue): number => {
	const r = q.data[q.head];
	q.head ++;
	if (q.head >= q.size) {
		q.head = 0;
	}
	return r;
}
```

## Double-ended queue