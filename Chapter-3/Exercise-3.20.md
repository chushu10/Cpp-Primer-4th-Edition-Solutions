# Exercise 3.20

Explain which iterator you used in the previous programs, and why.

**Answer**: In the previous program, see [Exercise 3.18](Exercise-3.18.md) and [Exercise 3.19](Exercise-3.19.md), I used two kinds of iterators:

- `vector<int>::const_iterator`, which is used to print the `vector`, because this kind of iterator cannot write elements.
- `vector<int>::iterator`, which is used to assign each element a new value, because this kind of iterator can write elements.