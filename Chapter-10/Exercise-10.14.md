# Exercise 10.14

What is the difference between the `map` operations `count` and `find`?

**Answer**:

- `count`: return the occurrence time of a specific key in `map` (always return 0 or 1 in a `map`, will return >1 in a `multimap`).
- `find`: return the iterator to the element if it exits in `map`, otherwise, return `end`.