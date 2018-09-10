# Exercise 7.38

Given the following declarations,

```cpp
void mainip(int, int);
double dobj;
```

what is the rank (Section 7.8.4, p. 272) of each conversion in the following calls?

(a) `manip('a', 'z');` (b) `mainip(55.4, dobj);`

**Answer**:

(a) Match through a promotion, `char` to `int`;
(b) Match through a standard conversion, `double` to `int`.