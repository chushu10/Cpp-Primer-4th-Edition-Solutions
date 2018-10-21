# Exercise 10.4

Give illustrations on when a `list`, `vector`, `deque`, `map`, and `set` might be most useful.

**Answer**:

- `list`: sorting, which needs a lot of inserting and deleting of elements in the middle of the `list`.
- `vector`: shopping history, which needs random access of the history data. Because the history will not be changed, so we only need to insert elements at the back of the `vector`.
- `deque`: queue, which needs a lot of inserting and deleting of elements at the front or the back of the `deque`.
- `map`: dictionary and the alike.
- `set`: filter to discard duplicated words.