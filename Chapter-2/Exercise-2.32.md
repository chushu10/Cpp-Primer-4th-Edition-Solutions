# Exercise 2.32

Which of the following declarations and definitions would you put in a header? Explain why.

(a) `int var;`
(b) `const double pi = 3.1416;`
(c) `extern int total = 255;`
(d) `const double sq2 = sqrt(2.0);`

**Answer**:

- [ ] (a) is a definition which should not be put in a header;
- [x] (b) is a `const` objects whose value is known at compile time(initialized by constant expression), it can be put in a header file;
- [ ] (c) is a definiton which should not be put in a header;
- [x] (d) is a `const` objects whose value is known at compile time(initialized by constant expression), it can be put in a header file;