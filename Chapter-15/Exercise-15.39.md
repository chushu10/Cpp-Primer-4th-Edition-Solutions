# Exercise 15.39

Given that `s1`, `s2`, `s3` and `s4` are all `string`s, determine what objects are created in the following uses of the `Query` class:
(a) `Query(s1) | Query(s2) & ~ Query(s3);`
(b) `Query(s1) | (Query(s2) & ~ Query(s3));`
(c) `(Query(s1) & (Query(s2)) | (Query(s3) & Query(s4)));`

**Answer**:

(a) An `AndQuery`, a `OrQuery`, a `NotQuery` and three `WordQuery`s.
(b) The same as (a)
(c) Two `AndQuery`s, a `OrQuery`, and four `WordQuery`s.