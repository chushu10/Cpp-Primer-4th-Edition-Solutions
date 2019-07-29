# Exercise 16.33

Explain how the `next` pointers in the newly created `Queue` get set during the `copy_elems` function.

**Answer**:

1. When copying the first element, the newly created `Queue` is empty. So that the `next` pointer points to `0`.
2. When copying the elements after the first, the `Queue` is not empty. So that the `next` pointer of `tail` is set to `pt`.
