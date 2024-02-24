# Selection sort

## Behavior

In each iteration, the algorithm performs comparisons to determine the key element.
The key element of an iteration is simply the smallest or largest of that iteration.

Once every element has been compared, and the key element is determined, the key element is swapped into the partially sorted memory.

To sort in ascending order, the key element would be the smallest element, and the partially sorted memory lies at the front.

## Performance

This sorting algorithm performs a many comparisons, but it performs very few swaps in exchange.

Given an input sequence $a$ which contains $n$ unsorted elements, we can imagine the worst-case scenario as follows.

In first iteration, the algorithm performs $n-1$ comparisons and one swap.

In the second iteration, the algorithm performs $n-2$ comparisons and one swap, and so on.

Finally, in the final iteration, the algorithm performs one comparison and one swap.

The number of comparisons required is $(n-1)+(n-2)+\ldots+1\approx O(n^{2})$.
However, the number of swaps required is only $n-1\approx O(n)$.

Then, it stands to reason that this sorting algorithm performs well when input can be compared efficiently, but difficult to swap.

## References

- Selection sort (Wikipedia): https://en.wikipedia.org/wiki/Selection_sort

- Selection sort (geeksforgeeks): https://www.geeksforgeeks.org/selection-sort/
