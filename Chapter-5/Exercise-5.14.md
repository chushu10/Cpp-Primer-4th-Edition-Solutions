# Exercise 5.14

Although the following are legal, they probably do not behave as the programmer expects. Why? Rewrite the expressions as you think they should be.

(a) `if (ptr = retrieve_pointer() != 0)`
(b) `if (ival = 1024)`
(c) `ival += ival + 1;`

**Answer**:

(a) `if ((ptr = retrieve_pointer()) != 0)`
(b) `if (ival == 1024)`
(c) `ival += 1;`