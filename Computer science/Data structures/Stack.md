# Stack

**Definition**: A **stack** is an ordered collection of items. Two essential operations are defined on a stack: **push** and **pop**.

The **push** operation adds an element onto the top of the stack, and the **pop** operation removes the top-most element from the stack. Such an order is called **last-in-first-out**.

## Implementation

A stack can be represented with an **array** or a **linked list** with two exposed operations.

### Array

An array representation of a stack has to keep track of of some attributes. Namely, the position of the top-most element, the stack size, and the actual data itself.

```ts
//typescript
type Stack {
	top: number;
	size: number;
	data: (Object|null)[];
}
```

A minimal constructor for stacks can be implemented as:

```ts
//typescript
const initStack = (size: number): Stack => {
	const data = [];
	for (let i = 0; i < size; i ++) {
		data[i] = null;
	}
	return {
		top: -1,
		size,
		data,
	}
}
```

The minimal **push** operation can be implemented as:

```ts
//typescript
const push = (stk: Stack, element: Object): void => {
	if (stk.top + 1 >= stk.size) {
		return;
	}
	stk.data[stk.top + 1] = element;
	stk.top++; 
}
```

The minimal **pop** operation can be defined as:

```ts
//typescript
const pop = (stk: Stack): Object => {
	if (stk.top === - 1) {
		return;
	}
	const popped = stk.data[stk.top];
	stk.top--;
	return popped;
}
```

### Linked list

A linked list representation of a stack can be implemented with less attribute:

```ts
// typescript
type LinkedList = 
	| { next: LinkedList, data: Object }
	| null
```

