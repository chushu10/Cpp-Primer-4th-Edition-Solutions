# Exercise 9.3

Explain the differences between the constructor that takes a container to copy and the constructor that takes two iterators.

**Answer**:

We can use the constructor that takes two iterators to copy a container that we could not copy directly. More importantly, we can use it to copy only a sub-sequence of the other container.