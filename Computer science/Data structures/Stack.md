# Stack

**Definition**: A **stack** is an ordered collection of elements. Elements of a stack are removed in the reserved order in which they are inserted, called **last-in-first-out**. In practice, a stack can be implemented as a specialized **array**.

A stack data structure can be represented with three attributes: stack size, top position, and an array or other data structure to store the data. 

**Definition**: The **PUSH** operation adds an element onto the top of the stack. **Pushing** an element onto a full stack results in an error called **stack overflow**.

**Definition**: The **POP** operation removes the top-most element from the stack. **Popping** an element from an empty stack results in an error called **stack underflow**.

**Definition**: The **EMPTY** query checks whether a stack is empty or not.

The stack operations have $O(1)$ time complexity.

## Implementation

In TypeScript, a stack can be implemented as a object with three attributes: **size**, **top**, and **data**.

```ts
type Stack {
	size: number;
	top: number;
	data: number[];
}
```

The **top** attribute is initialized to **-1** to signify that the stack is empty.

```ts
const initStack = (size: number): Stack => {
	return {
		size,
		top: -1,
		data: [],
	};
}
```

A minimal **EMPTY** query is implemented as follows:

```ts
const isEmpty = (stk: Stack): bool => {
	return stk.top === -1;
} 
```

The minimal **PUSH** operation which handles **stack overflow** error can be implemented as follows:

```ts
const push(stk: Stack, element: number): void => {
	if (stk.top + 1 >= stk.size) {
		return;
	}
	stk.top++;
	stk.data[stk.top] = element;
}
```

The minimal **POP** operation which handles **stack underflow** error can be implemented as follows:

```ts
const pop(stk: Stack): void => {
	if (isEmpty(stk)) {
		return;
	}
	stk.top--;
}
```