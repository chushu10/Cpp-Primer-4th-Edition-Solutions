# Exercise 11.23

List the five iterator categories and the operations that each supports.

**Answer**:

- Input iterator: Read, but not write; increment only.
- Output iterator: Write, but not read; increment only.
- Forward iterator: Read and write; increment only.
- Bidirectional iterator: Read and write; increment and decrement.
- Random access iterator: Read and write; full iterator arithmetic.

|               | Read | Write | Increment | Decrement | Random access |
|:--------------| :--: | :---: | :-------: | :-------: | :-----------: |
| Input         |   ✓  |       |     ✓     |           |               |
| Output        |      |   ✓   |     ✓     |           |               |
| Forward       |   ✓  |   ✓   |     ✓     |           |               |
| Bidirectional |   ✓  |   ✓   |     ✓     |     ✓     |               |
| Random access |   ✓  |   ✓   |     ✓     |     ✓     |       ✓       |