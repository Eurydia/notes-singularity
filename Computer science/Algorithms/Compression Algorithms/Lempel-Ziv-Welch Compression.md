# Lempel-Ziv-Welch Compression

Lempel-Ziv-Welch compression algorithm or LSW is a dictionary-based compression algorithm that takes advantage of recurring information with the input to save space.

Its key characteristics is that it can compress and decompress its input in a single pass. It achieves this behavior by keeping track of a dictionary, in fact, we do not even need to pass a look up table for the algorithm to decompress its input.

One important thing to note is that; the algorithm has to be seeded with a single-character sequence of each character in the uncompressed input. As such, in practice, we need to iterate over the input at least twice; first to seed the algorithm and second to perform the compression.

While it is true that we do not need to provide a look up table during decompression, we need to ensure that the algorithm for compression and decompression have the same seed.

## Compression

We will consider the following uncompressed input as an example;

$$
\begin{align*}
\text{ABABABAACAACCBBAAAAAAAAA}
\end{align*}
$$

We have the following seeded table;

| Sequence | Code | 
| -------- | ---- | 
| A        | 1    | 
| B        | 2    | 
| C        | 3    | 

From this, we construct the table

| Sequence | Code |
| -------- | ---- |
| A        | 1    |
| B        | 2    |
| C        | 3    |
| AB       | 4    |
| BA       | 5    |
| ABA      | 6    |
| ABAA     | 7    |
| AC       | 8    |
| CA       | 9    |
| AA       | 10   |
| ACC      | 11   |
| CB       | 12   |
| BB       | 13   |
| BAA      | 14   |
| AAA      | 15   |
| AAAA     | 16   |

Sequence

| Current Sequence | Next Character | Output |
| ---------------- | -------------- | ------ |
| NULL             | A              | -      |
| A                | B              | 1      |
| B                | A              | 2      |
| A                | B              | -      |
| AB               | A              | 4      |
| A                | B              | -      |
| AB               | A              | -      |
| ABA              | A              | 6      |
| A                | C              | 1      |
| C                | A              | 3      |
| A                | A              | 1      |
| A                | C              | -      |
| AC               | C              | 8      |
| C                | B              | 3      |
| B                | B              | 2      |
| B                | A              | -      |
| BA               | A              | 5      |
| A                | A              | -      |
| AA               | A              | 10     |
| A                | A              | -      |
| AA               | A              | -      |
| AAA              | A              | 15     |
| A                | A              | -      |
| AA               | A              | -      |
| AAA              | A              | 15     |

## Decompression

Consider the compression string and the seeded table

```
1 2 4 3 5 6 9 7 1
```

| Character | Code |
| --------- | ---- |
| A         | 1    |
| B         | 2    |
| C         | 3    |

We construct the uncompressed string as follows;

| Compressed | Uncompressed | Entry    | Conjecture |
| ---------- | ------------ | -------- | ---------- |
| 1          | A            | -        | 4: A?      |
| 2          | B            | 4:AB     | 5:B?       |
| 4          | AB           | 5:BA     | 6:AB?      |
| 3          | C            | 6:ABC    | 7:C?       |
| 5          | BA           | 7:CB     | 8:BA?      |
| 6          | ABC          | 8:BAA    | 9:ABC?     |
| 9          | ABCA         | 9:ABCA   | 10:ABCA?   |
| 7          | CB           | 10:ABCAC | 11:CB?     |
| 1          | A            | 11:CBA   | -          |

## Additional Example
### Example

Decode

1 2 4 3 5 8 1 10 11 1

A B AB C BA BAA A ABCAC CBA A


### Example 2

```
CBABABABCBABABAB
```

| Char | Code |
| ---- | ---- |
| A    | 1    |
| B    | 2    |
| C    | 3    |

Perform compression

| Char | Code |
| ---- | ---- |
| A    | 1    |
| B    | 2    |
| C    | 3    |
| CB   | 4    |
| BA   | 5    |
| AB   | 6    |
| BAB  | 7    |
| BABC | 8    |
| CBA  | 9    |
| ABA  | 10   |
| ABAB | 11   |

| Sequence | Next | Output |
| -------- | ---- | ------ |
| -        | C    | -      |
| C        | B    | 3      |
| B        | A    | 2      |
| A        | B    | 1      |
| B        | A    | -      |
| BA       | B    | 5      |
| B        | A    | -      |
| BA       | B    | -      |
| BAB      | C    | 7      |
| C        | B    | -      |
| CB       | A    | 4      |
| A        | B    | -      |
| AB       | A    | 6      |
| A        | B    | -      |
| AB       | A    | -      |
| ABA      | B    | 10     |
| B        | -    | 2      |


### Example 3

```
ABABCBAABCABCACBA
```

| Char | Code |
| ---- | ---- |
| A    | 1    |
| B    | 2    |
| C    | 3    |
| AB   | 4    |
| BA   | 5    |
| ABC  | 6    |
| CB   | 7    |
| BAA  | 8    |
| ABCA | 9    |
| CBA  | 10   |

| Seq  | Char | Output |
| ---- | ---- | ------ |
| -    | A    | -      |
| A    | B    | 1      |
| B    | A    | 2      |
| A    | B    | -      |
| AB   | C    | 4      |
| C    | B    | 3      |
| B    | A    | -      |
| BA   | A    | 5      |
| A    | B    | -      |
| AB   | C    | -      |
| ABC  | A    | 6      |
| A    | B    | -      |
| AB   | C    | -      |
| ABC  | A    | -      |
| ABCA | C    | 9      |
| C    | B    | -      |
| CB   | A    | 7      |
| A    | -    | 1      |
