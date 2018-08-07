# Exercise 6.6

What is a "dangling else"? How are `else` clauses resolved in C++?

**Answer**:

To be frank, a "dangling else" is the `else` we are not sure to which `if` it belongs. The `else` clauses resolved to its nearest `if` statement.