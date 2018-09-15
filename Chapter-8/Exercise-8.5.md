# Exercise 8.5

What causes the following `while` to terminate?

`while (cin >> i) /* ... */`

**Answer**:

When the state of the `istream` type `cin` is any of `bad, fail` or `eof`.