# Exercise 4.1

Assuming `get_size` is a function that takes no arguments and returns an `int` value, which of the following definitions are illegal? Explain why.

`unsigned buf_size = 1024;`

(a) `int ia[buf_size];`
(b) `int ia[get_size()];`
(c) `int ia[4 * 7 - 14];`
(d) `char st[11] = "fundamental";`

**Answer**:

(a) is illegal, because `buf_size` is a non `const` variable whose value cannot be known until run time;
(b) is illegal, because the return value of `get_size` cannot be known until run time;
(c) is legal, because the result of `4 * 7 - 14` can be calculated in compile time;
(d) is illegal, because string literal "fundamental“ has 11 characters and 1 null terminator, which exceeds the dimension of array `st`.