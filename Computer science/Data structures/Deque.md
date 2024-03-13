# Deque

**Definition**: A **Deque** is an ordered collection of elements. Elements of a deque can be added or removed from the front and the back.

Queues and stacks can be thought of as specialized deques.

## Common operations

**Definition**: The **PUSH FRONT** operation adds an element to the back of a deque.

**Definition**: The **PUSH LAST** operation adds an element to the start of a deque.

**Definition**: The **POP FIRST** operation removes the first element of a deque.

**Definition**: The **POP LAST** operation removes the last element of a deque.

**Definition**: The **PEEK FIRST** query returns the first element of a deque.

**Definition**: The **PEEK LAST** query returns the last element of a deque.

### Complexity

The time complexity of deque operations is $O(1)$ with the assumption that there is no memory allocation and deallocation cost overhead.

Indexing a random element of a deque has $O(n)$ time complexity where $n$ is the size of the deque.

