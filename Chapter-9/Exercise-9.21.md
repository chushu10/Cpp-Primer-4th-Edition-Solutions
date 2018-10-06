# Exercise 9.21

Assuming `c1` and `c2` are containers, what constraints does the following usage place on the element types in `c1` and `c2`?

`if (c1 < c2)`

What, if any, constraints are there on `c1` and `c2`?

**Answer**:

1. The containers must be the same kind of container and must hold elements of the same type.
2. The relational operators `<` should be defined with the element types of these containers.