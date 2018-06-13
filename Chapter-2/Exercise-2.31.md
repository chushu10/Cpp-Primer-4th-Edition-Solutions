# Exercise 2.31

Identify which of the following statements are declarations and which ones are definitions. Explain why they are declarations or definitions.

(a) `extern int ix = 1024;`
(b) `int iy;`
(c) `extern int iz;`
(d) `extern const int &ri;`

**Answer**:

(a) is definition, though it has `extern` keyword, it has initializer that makes it definition;
(b) is definition, because it has no `extern` keyword;
(c) is declaration, because it has `extern` keyword and no initializer;
(d) is declaration, the same reason as (c).