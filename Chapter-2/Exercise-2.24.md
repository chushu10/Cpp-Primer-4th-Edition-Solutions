# Exercise 2.24

Which of the following definitions, if any, are invalid? Why? How would you correct them?

(a) `int ival = 1.01;` (b) `int &rval1 = 1.01;`
(c) `int &rval2 = ival;` (d) `const int &rval3 = 1;`

**Answer**: (b) is invalid, because literal `1.01` is a const value, you can't initialize a non-const reference with a const value. Others are valid.