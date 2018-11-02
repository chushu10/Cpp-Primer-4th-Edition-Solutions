# Exercise 11.4

Assuming v is a `vector<double>` what, if anything, is wrong with calling `accumulate(v.begin(), v.end(), 0)`?

**Answer**:

Passing the 3rd argument `0` will imply that it is an `int` type, however the elements in `v` are `double`s.