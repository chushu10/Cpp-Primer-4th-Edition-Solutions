# Exercise 9.29

Explain the difference between a `vector`'s capacity and its size. Why is it necessary to support the notion of capacity in a container that stores elements continuously but not, for example, in a `list`?

**Answer**:

- **Capacity vs. Size**: The size is the number of elements in the `vector`; capacity is how many it could hold before new space must be allocated.
- **Why capacity necessary**: The reason is that library implementors use allocation strategies that minimize the costs of storing elements continuously, and capacity is essential to these allocation strategies. However, a `list` doesn't need to store elements continuously, so it won't be necessary to have capacity in a `list`.
