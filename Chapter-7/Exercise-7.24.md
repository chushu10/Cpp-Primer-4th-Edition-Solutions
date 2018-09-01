# Exercise 7.24

Which, if any, of the following declarations are errors? Why?

(a) `int ff(int a, int b = 0, int c = 0);`
(b) `char *init(int ht = 24, int wd, char bckgrnd);`

**Answer**:

(a) is ok.
(b) is in error, because when `ht` is default argument then all the arguments follow it should have default initializer.