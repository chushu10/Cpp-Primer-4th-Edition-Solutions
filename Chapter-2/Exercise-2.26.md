# Exercise 2.26

What are the differences among the definitions in (a) and the assignments in (b)? Which, if any, are illegal?

(a) `int ival = 0;`
    `const int &ri = 0;`

(b) `ival = ri;`
    `ri = ival;`

**Answer**: (b) is illegal, you can't assign a non-const value `ival` to a const reference `ri`.