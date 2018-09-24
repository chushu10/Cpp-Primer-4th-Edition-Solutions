# Best Practices

| Sequential Containers |    |
| :-------------------- | :- |
| vector | Supports fast random access |
| list   | Supports fast insertion/deletion |
| deque  | Double-ended queue |

| Sequential Container Adaptors |    |
| :---------------------------- | :- |
| stack | Last in/First out stack |
| queue | First in/First out queue |
| priority_queue | Priority-managed queue |

- For reasons that shall become clear shortly, the most commonly used container constructor is the default constructor. In most programs, using the default constructor gives the best run-time performance and makes using the container easier.
- Two constraints of the type a container can hold:
  - The element type must support assignment.
  - We must be able to copy objects of the element type.
- We must separate the two closing `>` symbols with a space to indicate that these two characters represent two symbols. Without the space, `>>` is treated as a single symbol, the right shift operator, and results in a compile-time error.