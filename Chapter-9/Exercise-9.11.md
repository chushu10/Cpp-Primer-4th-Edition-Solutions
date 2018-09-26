# Exercise 9.11

What are the constraints on the iterators that form iterator ranges?

**Answer**:

Two iterators, `first` and `last`, form an iterator range, if:

- They refer to elements of, or one-past-the-end of, **the same container**.
- If the iterators are not equal, then it must be possible to reach `last` by repeatedly incrementing `first`. In other words, last must **not precede** first in the container.