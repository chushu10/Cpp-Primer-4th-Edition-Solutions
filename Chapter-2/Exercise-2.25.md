# Exercise 2.25

Given the preceeding definitions, which, if any, of the following assignments are invalid? If they are valid, explain what they do.

(a) `rval2 = 3.14159;` (b) `rval2 = rval3;`
(c) `ival = rval3;` (d) `rval3 = ival;`

**Answer**:
(a) is valid, it assigns 3 to `ival` and `rval2`(alias to `ival`);
(b) is valid, it assigns 1 to `ival` and `rval2`(alias to `ival`);
(c) is valid, it assigns 1 to `ival`;
(d) is invalid, you can't assign a non-const value to a const reference.