# Exercise 2.23

Which of the following are legal? For those usages that are illegal, explain why.

(a) `const int buf;`
(b) `int cnt = 0;`
    `const int sz = cnt;`
(c) `cnt++; sz++;`

**Answer**: (a) is illegal, cause `const` cannot be uninitialized; (b) is legal; (c) is illegal, cause `sz` is `const`, it cannot be modified.