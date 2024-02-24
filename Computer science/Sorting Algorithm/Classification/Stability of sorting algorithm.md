# Stability of sorting algorithm

From the following input which contains some integers,

$$
\begin{align*}
120, 12, 36, 90, 70, 14
\end{align*}
$$

We want to sort it in ascending order based on the left-most digit.

## Unstable algorithm

Let's imagine a sorting algorithm $\mathcal{A}$, it produces the following output.

$$
14, 12, 120, 36, 70, 90
$$

This output is sorted based on the description given.

In this scenario, $\mathcal{A}$ is unstable, because, in the original input, 120 appears before 12, and 12 before 14, so we expect the same for the output.
However, the output produced by $\mathcal{A}$, 120 does not appear before 12 and 12 does not appear before 14.

Thus, the soring algorithm $\mathcal{A}$ is unstable.

### Stable algorithm 

Let's imagine a different sorting algorithm $\mathcal{B}$ on the same input, it produces the following output.

$$
\begin{align*}
120, 12, 14, 36, 70, 90
\end{align*}
$$

This output is sorted based on the description given.

In this scenario, $\mathcal{B}$ is stable, because, the order of 120, 12, and 14 is preserved.

Thus, the soring algorithm $\mathcal{B}$ is stable.


## References

- Stability (Wikipedia): https://en.wikipedia.org/wiki/Sorting_algorithm#Stability
- Stable and Unstable Sorting Algorithms (geeksforgeeks): https://www.geeksforgeeks.org/stable-and-unstable-sorting-algorithms/