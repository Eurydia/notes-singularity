# Bubble sort

> [!cite] Sources
>
> - [Bubble sort (Wikipedia)](https://en.wikipedia.org/wiki/Bubble_sort)

Bubble sort is a comparison based sorting algorithm.

Its worst case performance is 
- $O(n^{2})$ comparisons
- $O(n^{2})$ swaps

## Bubble sort algorithm description

This description sorts a sequence of $n$ elements into ascending order.

It compares the first element against the second element. 
Based on the result of the comparison, it:
- swaps the first element with the second element if the first element is "greater" than the second element.
- Otherwise, it does nothing.

Then, it compares the second element against the third element, and swap them if necessary.
This process repeats until it reaches the second last element of the working region.

After it compares the second last element of the working region against the last element of the working region, and swap them if necessary, the working region is decreased by one from the back, and the first step is repeated.

It terminates when the size of working region is one.

### Bubble sort in action

We will sort this sequence into an ascending order using bubble sort.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 5   | 4   | 1   |

We start by comparing the first element against the second element.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 5   | 4   | 1   |
|       | ^   | ^   |     |     |     |

The first element is greater, so we swap them.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 5   | 4   | 1   |
|       | >   | <   |     |     |     |

Next, we compare the second element against the third element.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 5   | 4   | 1   |
|       |     | ^   | ^   |     |     |

The second element is not greater element, so we leave them as is. 

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 5   | 4   | 1   |
|       |     | -   | -   |     |     |

Next, we compare the third element against the fourth element.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 5   | 4   | 1   |
|       |     |     | ^   | ^   |     |

The third element is greater, so we swap them.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 4   | 5   | 1   |
|       |     |     | >   | <   |     |

Next, we compare the fourth element against the fifth element.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 4   | 5   | 1   |
|       |     |     |     | ^   | ^   |

The fourth element is greater, so we swap them.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 4   | 1   | 4   |
|       |     |     |     | >   | <   |

There is no element to compare against the last element, so we decrease the working region by one.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 3   | 2   | 4   | 1   | 5   |
|       |     |     |     |     | x   |

The size of our working region is greater than one, so we start over.

We compare the first element against the second element.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 4   | 1   | 5   |
|       | ^   | ^   |     |     | x   |

The first element is not greater, so we leave them as is.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 4   | 1   | 5   |
|       | -   | -   |     |     | x   |

Next, we compare the second element against the third element.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 4   | 1   | 5   |
|       |     | ^   | ^   |     | x   |

The second element is not greater, so we leave them as is.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 4   | 1   | 5   |
|       |     | -   | -   |     | x   |

Next, we compare the third element against the fourth element.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 4   | 1   | 5   |
|       |     |     | ^   | ^   | x   |

The third element is greater, so we swap them.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 1   | 4   | 5   |
|       |     |     | >   | <   | x   |

There is no element to compare against the last element, so we decrease the working region by one.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 1   | 4   | 5   |
|       |     |     |     | x   | x   |

The size of our working region is greater than one, so we start over.

We compare the first element against the second element.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 1   | 4   | 5   |
|       | ^   | ^   |     | x   | x   |

The first element is not greater, so we leave them as is.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 1   | 4   | 5   |
|       | -   | -   |     | x   | x   |

Next, we compare the second element against the third element.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 3   | 1   | 4   | 5   |
|       |     | ^   | ^   | x   | x   |

The second element is greater, so we swap them.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 1   | 3   | 4   | 5   |
|       |     | >   | <   | x   | x   |

There is no element to compare against the last element, so we decrease the working region by one.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 1   | 3   | 4   | 5   |
|       |     |     | x   | x   | x   |

The size of our working region is greater than one, so we start over.

We compare the first element against the second element.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 2   | 1   | 3   | 4   | 5   |
|       | ^   | ^   | x   | x   | x   |

The first element is greater, so we swap them.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 2   | 3   | 4   | 5   |
|       | >   | <   | x   | x   | x   |

There is no element to compare against the last element, so we decrease the working region by one.

| Index | 0   | 1   | 2   | 3   | 4   |
| ----- | --- | --- | --- | --- | --- |
| Value | 1   | 2   | 3   | 4   | 5   |
|       |     | x   | x   | x   | x   |

The size of our working region is one, so the algorithm terminates.

## Implementations of bubble sort

The implementations sort a sequence in place in ascending order.

### JavaScript

```javascript
const bubble_sort = (xs: Array<number>, size: number): void => {
	let offset, k, a, b;
	for (offset = 0; offset < size; offset ++) {
		for (k = 0; k < size - offset - 1; k ++) {
			a = xs[k];
			b = xs[k + 1];
			if (a > b) {
				xs[k] = b;
				xs[k + 1] = a;
			}
		}
	}
```

### Python

```python
def bubble_sort(xs: list[int], size: int) -> None:
	for offset in range(size - 1):
		for k in range(size - offset - 1):
			a: int = xs[k]
			b: int = xs[k + 1] 
			if a > b:
				xs[k] = b
				xs[k + 1] = a
```

### C

```C
void bubble_sort(int[] xs, size_t size) {
	int offset, k, a, b;
	for (offset = 0; offset < size; offset ++) {
		for (k = 0; k < size - offset - 1; k ++) {
			a = xs[k];
			b = xs[k + 1];
			if (a > b) {
				xs[k] = b;
				xs[k + 1] = a;
			}
		}
	}	
}
```