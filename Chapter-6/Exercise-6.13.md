# Exercise 6.13

Explain in detail how the statement in the `while` loop is executed:

`*dest++ = *source++`;

**Answer**:

It executes either from left to right or right to left, there is no fixed order. Suppose it executes from left to right, here is the execution sequence:

1. Post fix `++` has higher precedence than `*`, so that post fix `++` applies to `dest` to get the older version of `dest`.
2. `*` applies to the older version of `dest` to get the a lvalue.
3. Like before, pst fix `++` has higher precedence than `*`, so that post fix `++` applies to `source` to get the older version of `source`.
4. `*` applies to the older version of `source` to get the a lvalue.
5. Assign the right hand lvalue to the left handlvalue, so that the value of older `dest` is assigned by the value of older `source`.