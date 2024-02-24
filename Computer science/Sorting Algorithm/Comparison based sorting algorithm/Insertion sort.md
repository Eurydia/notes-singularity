# Insertion sort

> [!cite] Sources
>
> - [Insertion sort (Wikipedia)](https://en.wikipedia.org/wiki/Insertion_sort)

Worst case performance:
- $O(n^{2})$ comparisons
- $O(n^{2})$ swaps

## Insertion sort algorithm description

The algorithm selects an element as a pivot.

It inserts the pivot behind the first element that is smaller than itself.
Before the pivot can be inserted, the partially sorted elements have to be shifted to make room.

After the pivot has been inserted, the working region is decreased by one.

It terminates when the working region is zero.

### Insertion sort in action

We will sort this sequence into an ascending order using insertion sort.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 5   | 4   | 1   |

We say that the first element is already in the correct position.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (3) | 2   | 5   | 4   | 1   |

Next, we select the second element to be the pivot.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (3) | 2   | 5   | 4   | 1   |
|       |     | !   |     |     |     |

The pivot is temporarily stored outside the sequence.

| Pivot index | 1   |
| ----------- | --- |
| Pivot value | 2   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (3) | -   | 5   | 4   | 1   |

Next, we try to find the first element smaller than the pivot.

We start by comparing the pivot against the first element.

| Pivot index | 1   |
| ----------- | --- |
| Pivot value | 2   |
|             | ^   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (3) | -   | 5   | 4   | 1   |
|       | ^   |     |     |     |     |

The first element not smaller than the pivot, so the pivot will be inserted at the front-most position.

| Pivot index | 1   |
| ----------- | --- |
| Pivot value | 2   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (3) | -   | 5   | 4   | 1   |

The front-most position is occupied, so other elements has to be shifted to the right to make room.

The first element is shifted to the right.

| Pivot index | 1   |
| ----------- | --- |
| Pivot value | 2   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (-  | 3)  | 5   | 4   | 1   |
|       | >   | <   |     |     |     |

The pivot is inserted at the front-most position.

| Pivot index | -   |
| ----------- | --- |
| Pivot value | -   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3)  | 5   | 4   | 1   |

Next, we select the third element to be the pivot.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3)  | 5   | 4   | 1   |
|       |     |     | !   |     |     |

The pivot is temporarily stored outside the sequence.

| Pivot index | 2   |
| ----------- | --- |
| Pivot value | 5   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3)  | -   | 4   | 1   |

Next, we try to find the first element smaller than the pivot.

We start by comparing the pivot against the second element.

| Pivot index | 2   |
| ----------- | --- |
| Pivot value | 5   |
|             | ^   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3)  | -   | 4   | 1   |
|       |     | ^   |     |     |     |

The second element is smaller than the pivot, so the pivot will be inserted after it.

| Pivot index | -   |
| ----------- | --- |
| Pivot value | -   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | 5)  | 4   | 1   |

Next, we select the fourth element as the pivot.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | 5)  | 4   | 1   |
|       |     |     |     | !   |     |

The pivot is temporarily stored outside the sequence.

| Pivot index | 3   |
| ----------- | --- |
| Pivot value | 4   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | 5)  | -   | 1   |
|       |     |     |     |     |     |

Next, we try to find the first element smaller than the pivot.

We start by comparing the pivot against the third element of the working region.

| Pivot index | 3   |
| ----------- | --- |
| Pivot value | 4   |
|             | ^   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | 5)  | -   | 1   |
|       |     |     | ^   |     |     |

The third element is greater than the pivot, so we move on to the second element of the working region.

| Pivot index | 3   |
| ----------- | --- |
| Pivot value | 4   |
|             | ^   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | 5)  | -   | 1   |
|       |     | ^   |     |     |     |

The second element is smaller than the pivot, so the pivot will be inserted after it in the third position.

| Pivot index | 3   |
| ----------- | --- |
| Pivot value | 4   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | 5)  | -   | 1   |

The third position is occupied, so the third element has to be shifted to the right to make room.

| Pivot index | 3   |
| ----------- | --- |
| Pivot value | 4   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | -   | 5)  | 1   |
|       |     |     | >   | <   |     |

The pivot is inserted into the third position.

| Pivot index | -   |
| ----------- | --- |
| Pivot value | -   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | 4   | 5)  | 1   |

Next, we select the fifth element to be the pivot.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | 4   | 5)  | 1   |
|       |     |     |     |     | !   |

The pivot is temporarily stored outside the sequence.

| Pivot index | 4   |
| ----------- | --- |
| Pivot value | 1   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | 4   | 5)  | -   |

Next, we try to find the first element smaller than the pivot.

We start by comparing the pivot against the fourth element of the working region.

| Pivot index | 4   |
| ----------- | --- |
| Pivot value | 1   |
|             | ^   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | 4   | 5)  | -   |
|       |     |     |     | ^   |     |

The fourth element is not smaller than the pivot, so we look at the third element.

We compare the pivot against the third element.

| Pivot index | 4   |
| ----------- | --- |
| Pivot value | 1   |
|             | ^   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | 4   | 5)  | -   |
|       |     |     | ^   |     |     |

The third element is not smaller than the pivot, so we move to the second element.

We compare the pivot against the second element.

| Pivot index | 4   |
| ----------- | --- |
| Pivot value | 1   |
|             | ^   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | 4   | 5)  | -   |
|       |     | ^   |     |     |     |

The second element is not smaller than the pivot, so we look at the next element.

We compare the pivot against the first element.

| Pivot index | 4   |
| ----------- | --- |
| Pivot value | 1   |
|             | ^   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | 4   | 5)  | -   |
|       | ^   |     |     |     |     |

The first element is not smaller than the pivot, so the pivot will be inserted at the front-most position.

| Pivot index | 4   |
| ----------- | --- |
| Pivot value | 1   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | 4   | 5)  | -   |

The front-most position is occupied, so other elements has to be shifted to the right to make room.

The fourth element is shifted to the right.

| Pivot index | 4   |
| ----------- | --- |
| Pivot value | 1   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | 4   | -   | 5)  |
|       |     |     |     | >   | <   |

The third element is shifted to the right.

| Pivot index | 4   |
| ----------- | --- |
| Pivot value | 1   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | 3   | -   | 4   | 5)  |
|       |     |     | >   | <   |     |

The second element is shifted to the right.

| Pivot index | 4   |
| ----------- | --- |
| Pivot value | 1   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (2  | -   | 3   | 4   | 5)  |
|       |     | >   | <   |     |     |

The first element is shifted to the right.

| Pivot index | 4   |
| ----------- | --- |
| Pivot value | 1   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (-  | 2   | 3   | 4   | 5)  |
|       | >   | <   |     |     |     |

The pivot is inserted at the front-most position.

| Pivot index | -   |
| ----------- | --- |
| Pivot value | -   |

Working region:

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | (1  | 2   | 3   | 4   | 5)  |

Since there is no element left, the algorithm terminates.

### Implementations of insertion sort

#### Python

```Python
def insertion_sort(xs: list[int], size: int) -> None:
    for p_idx in range(1, size):
        i: int = p_idx

        while i > 0 and xs[i - 1] > xs[i]:
            temp = xs[i]
            xs[i] = xs[i - 1]
            xs[i - 1] = temp
            i -= 1
```

### JavaScript

```typescript
const insertionSort = (
	xs: number[],
	size: number,
	states: FrameStateData[][],
): void => {
	let p_idx, temp, mover;

	for (p_idx = 1; p_idx < size; p_idx++) {
		p_val = xs[p_idx];

		mover = p_idx;

		while (mover > 0 && xs[mover - 1] > p_val) {
			temp = xs[mover];
			xs[mover] = xs[mover - 1];
			xs[mover - 1] = temp;
			mover--;
		}
		
	}
};
```