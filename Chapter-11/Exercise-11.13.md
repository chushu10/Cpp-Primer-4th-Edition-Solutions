# Exercise 11.13

Explain the differences among the three insert iterators.

**Answer**:

- `back_inserter`, which creates an iterator that uses `push_back`.
- `front_inserter`, which uses `push_front`.
- `inserter`, which uses `insert`. In addition to a container, `inserter` takes a second argument: an iterator indicating the position ahead of which insertion should begin.