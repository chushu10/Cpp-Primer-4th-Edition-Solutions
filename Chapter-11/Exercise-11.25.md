# Exercise 11.25

What kinds of iterators do you think `copy` requires? What about `reverse` or `unique`?

**Answer**:

The first two parameters of `copy` should be at least input iterators, since we have to read elements from them. While the third parameter should be at least output iterator, because to have to write elements to it. Just look at the example code in [Exercise 11.16](Exercise-11.16.md), where we pass two input iterators and one output iterator to `copy`.

`reverse` requires bidirectional iterator, and `unique` requires forward iterator.