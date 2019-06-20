# Excercise 16.18

In this section we noted that we deliberately wrote the test in `compare` to avoid requiring a type to have both the `<` and `>` operators. On the other hand, we tend to assume that types will have both `==` and `!=`. Explain why this seeming discrepancy in treatment actually reflects good programming style.

**Answer**:

Because `==` and `!=` is guaranteed to be defined on all operators
