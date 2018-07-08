# Exercise 4.19

Explain the meaning of the following five definitions. Identify any illegal definitions.

(a) `int i;`
(b) `const int ic;`
(c) `const int *pic;`
(d) `int *const cpi;`
(e) `const int *const cpic;`

**Answer**:

(a) defines a `int` type object;
(b) defines a `int` type object which is a `const`, while it doesn't initialize `ic`, so it is **illegal**;
(c) defines a pointer to `int` object, and the pointer thinks that the `int` object it points to is a `const`;
(d) defines a `const` pointer that points to a `int` object, while it doesn't initialize `cpi`, so it is **illegal**;
(e) defines a `const` pointer that points to a `int` object, and the pointer thinks that the `int` object it points to is a `const`, while it doesn't initialize `cpic`, so it is **illegal**.