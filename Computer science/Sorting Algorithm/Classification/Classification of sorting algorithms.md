# Classification of sorting algorithms

> [!cite] Sources
> 
> - [Classification of sorting algorithm (Wikipedia)](https://en.wikipedia.org/wiki/Sorting_algorithm#Classification)

 A sorting algorithm may be classified based on its:
 - time complexity
 - space complexity
 - recursive/non-recursive/both
 - comparison-based/non-comparison-based
 - stable/unstable
 - serial/parallel
 - adaptability

## Time complexities

> [!cite] Sources
> - [Time complexity (Wikipedia)](https://en.wikipedia.org/wiki/Time_complexity)


The time complexity is the computational complexity that describes the amount of computer time it takes to run an algorithm. 

Time complexity is commonly estimated by counting the number of elementary operations, such as the number of operations, and swaps, performed by the algorithm.

Time complexity is expressed as a function of the size of the input.
More specifically, 

**Big O**

It expresses the greatest number of elementary operations (upper bound) that an algorithm can perform on an arbitrary input size.

Notation: $O(n)$ where $n$ represents the input size.

**Big Omega**

It expresses the least number of elementary operations (lower bound) that an algorithm can perform on an arbitrary input size.

Notation: $\Omega(n)$ where $n$ represents the input size.

## Stability

For any given sequence, a stable sorting algorithm will always yield the same sorted sequence.