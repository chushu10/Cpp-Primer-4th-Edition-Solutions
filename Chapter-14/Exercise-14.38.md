# Exercise 14.38

In the last call to `count_if` we used `not1` to negate the result from `bind2nd` of `(less_equal<int>(), 10)`. Why did we use `not1` rather than `not2` .

**Answer**:

Because `bind2nd` is a function adaptor that converts a binary function object into a unary function object. `not1` reverses the truth value of a unary predicate function object, and `not2` reverses the truth value of a binary predicate function object.