# Exercise 5.29

Given that `ptr` points to a class with an `int` member named `ival`, `vec` is a `vector` holding `int`s, and that `ival`, `jval`, and `kval` are also `int`s, explain the behavior or each of these expressions. Which, if any, are likely to be incorrect? Why? How might each be corrected?

(a) `ptr->ival != 0`
(b) `ival != jval < kval`
(c) `ptr != 0 && *ptr++`
(d) `ival++ && ival`
(e) `vec[ival++] <= vec[ival]`

**Answer**:

(a) `ptr->ival != 0` is likely to be incorrect, because we don't know whether `ptr` points to NULL or not. The correction might be `ptr && (ptr->ival != 0)`
(b) `ival != jval < kval` is misleading, it should be `ival != jval && jval < kval`
(c) `ptr != 0 && *ptr++` is correct. Because `ptr++` return the older version of `ptr`, and we know that `ptr != 0`. So it's safe to dereference `ptr` and increment `ptr` by one.
(d) `ival++ && ival` is not likely to be incorrect, because the code will be executed from left to right.
(e) `vec[ival++] <= vec[ival]` is likely to be incorrect. Because the operands of `<=` operator are treated equally, the code not determined to execute from left to right. So we may get `true` on one machine while `false` on another.