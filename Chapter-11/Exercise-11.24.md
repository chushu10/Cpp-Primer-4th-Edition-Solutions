# Exercise 11.24

What kind of iterator does a `list` have? What about a `vector`?

**Answer**:

A `list` must at least have a bidirectional iterator, because we need to both increment and decrement the iterator to access all the elements. A `vector` must at least have a random access iterator, because we also need random access in a `vector`.