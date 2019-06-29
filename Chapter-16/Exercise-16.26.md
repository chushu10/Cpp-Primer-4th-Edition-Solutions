# Exercise 16.26

Given the following template definition for `sum`

```cpp
template <class T1, class T2, class T3> T1 sum(T2, T3);
```

explain each of the following calls. Indicate which, if any, are errors. For each error, explain what is wrong.

```cpp
double dobj1, dobj2; float fobj1, fobj2; char cobj1, cobj2;
(a) sum(dobj1, dobj2);
(b) sum<double, double, double>(fobj1, fobj2);
(c) sum<int>(cobj1, cobj2);
(d) sum<double, ,double>(fobj2, dobj2);
```

**Answer**:

`(b)` and `(c)` are both OK.
`(a)` should be `sum<double>(dobj1, dobj2)`
`(d)` should be `sum<double, double>(fobj2, dobj2)` or `sum<double, double, double>(fobj2, dobj2)`, the latter is preferred.
