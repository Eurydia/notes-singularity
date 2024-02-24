# Heapsort

> [!cite] Sources
>
> - [Heapsort (Wikipedia)](https://en.wikipedia.org/wiki/Heapsort)

Worst case performance:
- $O(n\log n)$ comparisons

## Heapsort algorithm description

The algorithm works by creating a max heap within the sequence.

A heap is a binary-tree-like structure.
In this particular case, the parent is strictly greater than its children.

Once a heap is formed, the first and last elements of the working region are swapped.

Incidentally, the first element of the working region is the largest of element as well.
The working region is decreased by one.

The heap is rebuilt, we swap the first and last elements, and then we decrease the size of the working region by one.

The algorithm terminates once the size of the working region is one.

### Building the heap

The heart of heapsort lies in the building and rebuilding of the max heap.

Initially, the heap is constructed starting from the last element.
And the reconstruction is done every iteration.

Note that the construction and reconstruction require different two procedures.

### Example

For the sake of brevity, let's define a term *start-end working region* for 1-index sequence.

The term *1-3 working region* refers to the subsequence which includes the first element, the second element and the third element.

Similarly, the term *1-2 working region* refers to the subsequence which includes the first element and the second element.

#### Example: Heapsort in action

We will sort this sequence into an ascending order sequence using heapsort.

The initial sequence will be referred to as *0-4 working region*.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 5   | 4   | 1   |

We will start by constructing the initial max heap.

We consider the last element, and assume that it is a parent.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 5   | 4   | 1   |
|       |     |     |     |     | P   |

Since it does not have a child, so we do not consider it further.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 5   | 4   | 1   |

Next, we consider the second to last element, and assume that it is a parent.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 5   | 4   | 1   |
|       |     |     |     | P   |     |

Since it does not have a child, so we do not consider it further.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 5   | 4   | 1   |

Next, we consider the third to last element, and assume that it is a parent.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 5   | 4   | 1   |
|       |     |     | P   |     |     |

Since it does not have a child, so we do not consider it further.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 5   | 4   | 1   |

Next, We consider the fourth to last element, and assume that it is a parent.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 5   | 4   | 1   |
|       |     | P   |     |     |     |

Its left child is the fourth element, and its right child is the fifth element.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 5   | 4   | 1   |
|       |     | P   |     | lC  | rC  |

Next, we compare its chilren.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 5   | 4   | 1   |
|       |     | P   |     | lC  | rC  |
|       |     |     |     | ^   | ^   |

The left child is greater, so we mark it.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 5   | 4   | 1   |
|       |     | P   |     | lC  | rC  |
|       |     |     |     | ^   |     |

Next, we compare the parent against its marked child.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 5   | 4   | 1   |
|       |     | P   |     | lC  | rC  |
|       |     | ^   |     | ^   |     |

The marked child is greater, so we swap them.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 4   | 5   | 2   | 1   |
|       |     | P   |     | lC  | rC  |
|       |     | >   |     | <   |     |

Since the parent is swapped with its marked child, we consider the marked child as a parent once more.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 4   | 5   | 2   | 1   |
|       |     |     |     | P   |     |

It does not have a child, so we do not consider it further.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 4   | 5   | 2   | 1   |

Next, we consider the fifth to last element, and assume that it is a parent.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 4   | 5   | 2   | 1   |
|       | P   |     |     |     |     |

Its left child is the second element and its right child is the third element.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 4   | 5   | 2   | 1   |
|       | P   | lC  | rC  |     |     |

Next, we compare its children.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 4   | 5   | 2   | 1   |
|       | P   | lC  | rC  |     |     |
|       |     | ^   | ^   |     |     |

The right child is greater, so we mark it.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 4   | 5   | 2   | 1   |
|       | P   | lC  | rC  |     |     |
|       |     |     | ^   |     |     |

Next, we compare the parent against its marked child.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 4   | 5   | 2   | 1   |
|       | P   | lC  | rC  |     |     |
|       | ^   |     | ^   |     |     |

The marked child is greater, so we swap them.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 5   | 4   | 3   | 2   | 1   |
|       | P   | lC  | rC  |     |     |
|       | >   |     | <   |     |     |

Since the parent is swapped with its marked child, we consider the marked child as a parent once more.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 5   | 4   | 3   | 2   | 1   |
|       |     |     | P   |     |     |

It does not have a child, so we do not consider it further.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 5   | 4   | 3   | 2   | 1   |

We have completed our initial max heap construction.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 5   | 3   | 4   | 2   | 1   |

Next, we swap the first element with the last element of the working region.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 3   | 4   | 2   | 5   |
|       | >   |     |     |     | <   |

We decrease the size of our working region by one.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 3   | 4   | 2   | 5   |
|       |     |     |     |     | x   |

Since the size of our working region is greater than one, we need to reconstruct the heap starting from the beginning.

We consider the first element, and assume that it is a parent.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 3   | 4   | 2   | 5   |
|       | P   |     |     |     | x   |

Its left child is the second element, and its right child is the third element.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 3   | 4   | 2   | 5   |
|       | P   | lC  | rC  |     | x   |

Next, we compare its children

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 3   | 4   | 2   | 5   |
|       | P   | lC  | rC  |     | x   |
|       |     | ^   | ^   |     | x   |

The right child is greater, so we mark it.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 3   | 4   | 2   | 5   |
|       | P   | lC  | rC  |     | x   |
|       |     |     | ^   |     | x   |

Next, we compare the parent against its marked child.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 3   | 4   | 2   | 5   |
|       | P   | lC  | rC  |     | x   |
|       | ^   |     | ^   |     | x   |

The marked child is greater, so we swap them.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 4   | 3   | 1   | 2   | 5   |
|       | P   | lC  | rC  |     | x   |
|       | >   |     | <   |     | x   |

Since the parent is swapped with its marked child, we consider the marked child as a parent once more.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 4   | 3   | 1   | 2   | 5   |
|       |     |     | P   |     | x   |

Since it does not have a child, we do not consider it further.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 4   | 3   | 1   | 2   | 5   |
|       |     |     |     |     | x   |

Next, we consider the second element, and assume that it is a parent.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 4   | 3   | 1   | 2   | 5   |
|       |     | P   |     |     | x   |

Its left child is the fourth element, but its right child is outside the working region.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 4   | 3   | 1   | 2   | 5   |
|       |     | P   |     | lC  | x   |

Since the parent has one child, we do not compare the left and right child, but we mark the left child immediately.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 4   | 3   | 1   | 2   | 5   |
|       |     | P   |     | lC  | x   |
|       |     |     |     | ^   |     |

Next, we compare the parent against its marked child.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 4   | 3   | 1   | 2   | 5   |
|       |     | P   |     | lC  | x   |
|       |     | ^   |     | ^   |     |

The marked child is not greater, so we leave them as is.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 4   | 3   | 1   | 2   | 5   |
|       |     | P   |     | lC  | x   |
|       |     | -   |     | -   |     |

Next, we consider the third element, and assume that it is a parent.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 4   | 3   | 1   | 2   | 5   |
|       |     |     | P   |     | x   |

Since it does not have a child, we do not consider it further.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 4   | 3   | 1   | 2   | 5   |
|       |     |     |     |     | x   |

Next, we consider the fourth element, and assume that it is a parent.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 4   | 3   | 1   | 2   | 5   |
|       |     |     |     | P   | x   |

Since it does not have a child, we do not consider it further.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 4   | 3   | 1   | 2   | 5   |
|       |     |     |     |     | x   |

We have completed the reconstruction of the max heap.

Next, we swap the first element with the last element of the working region.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 1   | 4   | 5   |
|       | >   |     |     | <   | x   |

We decrease the size of our working region by one.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 1   | 4   | 5   |
|       |     |     |     | x   | x   |

Since the size of our working region is greater than one, we need to reconstruct the heap starting from the beginning.

We consider the first element, and assume that it is a parent.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 1   | 4   | 5   |
|       | P   |     |     | x   | x   |

It left child is the second element, and its right child is the third element.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 1   | 4   | 5   |
|       | P   | lC  | rC  | x   | x   |

Next, we compare its children.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 1   | 4   | 5   |
|       | P   | lC  | rC  | x   | x   |
|       |     | ^   | ^   | x   | x   |

The left child is greater, so we mark it.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 1   | 4   | 5   |
|       | P   | lC  | rC  | x   | x   |
|       |     | ^   |     | x   | x   |

Next, we compare the parent against its marked child.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 1   | 4   | 5   |
|       | P   | lC  | rC  | x   | x   |
|       | ^   | ^   |     | x   | x   |

The marked child is greater, so we swap them.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 1   | 4   | 5   |
|       | P   | lC  | rC  | x   | x   |
|       | >   | <   |     | x   | x   |

Since the parent is swapped with its marked child, we consider the marked child as a parent once more.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 1   | 4   | 5   |
|       |     | P   |     | x   | x   |

Since it does not have a child, we do not consider it further.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 1   | 4   | 5   |
|       |     |     |     | x   | x   |

Next, we consider the second element, and assume that it is a parent.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 1   | 4   | 5   |
|       |     | P   |     | x   | x   |

Since it does not have a child, we do not consider it further.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 1   | 4   | 5   |
|       |     |     |     | x   | x   |

Next, we consider the third element, and assume that it is a parent.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 1   | 4   | 5   |
|       |     |     | P   | x   | x   |

Since it does not have a child, we do not consider it further.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 1   | 4   | 5   |
|       |     |     |     | x   | x   |

We have completed the reconstruction of the max heap.

Next, we swap the first element with the last element of the working region.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 2   | 3   | 4   | 5   |
|       | >   |     | <   | x   | x   |

We decrease the size of our working region by one.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 2   | 3   | 4   | 5   |
|       |     |     | x   | x   | x   |

Since the size of our working region is greater than one, we need to reconstruct the heap starting from the beginning.

We consider the first element, and assume that it is a parent.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 2   | 3   | 4   | 5   |
|       | P   |     | x   | x   | x   |

Its left child is the second element, but its right child is outside the working region.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 2   | 3   | 4   | 5   |
|       | P   | lC  | x   | x   | x   |

Since the parent has one child, we do not compare the left and right child, but we mark the left child immediately.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 2   | 3   | 4   | 5   |
|       | P   | lC  | x   | x   | x   |
|       |     | ^   | x   | x   | x   |

Next, we compare the parent against its marked child.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 2   | 3   | 4   | 5   |
|       | P   | lC  | x   | x   | x   |
|       | ^   | ^   | x   | x   | x   |

The marked child is greater, so we swap them.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 1   | 3   | 4   | 5   |
|       | P   | lC  | x   | x   | x   |
|       | >   | <   | x   | x   | x   |

Since the parent is swapped with its marked child, we consider the marked child as a parent once more.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 1   | 3   | 4   | 5   |
|       |     | P   | x   | x   | x   |

Since it does not have a child, we do not consider it further.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 1   | 3   | 4   | 5   |
|       |     |     | x   | x   | x   |

We have completed the reconstruction of the max heap.

Next, we swap the first element with the last element of the working region.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 2   | 3   | 4   | 5   |
|       | >   | <   | x   | x   | x   |

We decrease the size of our working region by one.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 2   | 3   | 4   | 5   |
|       |     | x   | x   | x   | x   |

Since the size of our working region is not greater than one, the algorithm terminates.

## Implementations of heapsort

### Python

```python
def __heapsort_reconstruct(
    xs: list[int], size: int, parent_index: int
) -> None:
    while (2 * parent_index) + 1 < size:
        left_child_index: int = (2 * parent_index) + 1
        target_child: int = left_child_index

        if (left_child_index + 1 < size) and (
            xs[left_child_index] < xs[left_child_index + 1]
        ):
            target_child += 1

        if xs[parent_index] >= xs[target_child]:
            return

        temp: int = xs[parent_index]
        xs[parent_index] = xs[target_child]
        xs[target_child] = temp

        parent_index = target_child


def __heapsort_init_heap(xs: list[int], size: int) -> None:
    for i in reversed(range(size)):
        __heapsort_reconstruct(xs, size, i)


def heapsort(xs: list[int], size: int) -> None:
    __heapsort_init_heap(xs, size)

    for i in reversed(range(1, size)):
        temp = xs[0]
        xs[0] = xs[i]
        xs[i] = temp

        __heapsort_reconstruct(xs, i, 0)
```

### TypeScript

```typescript
const __heapsort_init_heap = (
	xs: number[],
	size: number,
): void => {
	for (let i = size - 1; i >= 0; i--) {
		__heapsort_rebuild(xs, size, i);
	}
};

const __heapsort_rebuild = (
	xs: number[],
	size: number,
	parentIndex: number,
): void => {
	while (parentIndex * 2 + 1 < size) {
		const leftChildIndex: number =
			parentIndex * 2 + 1;
		let targetChildIndex: number = leftChildIndex;

		if (
			leftChildIndex + 1 < size &&
			xs[leftChildIndex] < xs[leftChildIndex + 1]
		) {
			targetChildIndex++;
		}

		if (xs[parentIndex] >= xs[targetChildIndex]) {
			return;
		}

		const temp: number = xs[parentIndex];
		xs[parentIndex] = xs[targetChildIndex];
		xs[targetChildIndex] = temp;

		parentIndex = targetChildIndex;
	}
};

const heapsort = (
	xs: number[],
): void => {
	const size: number = xs.length;
	
	__heapsort_init_heap(xs, size, states);

	for (let i = size - 1; i > 0; i--) {
		const temp: number = xs[0];
		xs[0] = xs[i];
		xs[i] = temp;

		__heapsort_rebuild(xs, i, 0, states);
	}
};
```