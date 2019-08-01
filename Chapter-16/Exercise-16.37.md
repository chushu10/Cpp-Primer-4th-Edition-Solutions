# Exercise 16.37

Identify which, if any, of the following template instantiations are valid. Explain why the instantiation isn't valid.

```cpp
template <class T, int size> class Array { /* . . . */ };
template <int hi, int wid> class Screen { /* . . . */ };
```

(a) `const int hi = 40, wi = 80; Screen<hi, wi+32> sObj;`
(b) `const int arr_size = 1024; Array<string, arr_size> a1;`
(c) `unsigned int asize = 255; Array<int, asize> a2;`
(e) `const double db = 3.1415; Array<double, db> a3;`

**Answer**:

(a) and (b) are valid.

(c) is invalid, the compiler complaints:

```bash
ex1637.cc:9:38: error: non-type template argument is not a constant expression
unsigned int asize = 255; Array<int, asize> a2;
                                     ^~~~~
ex1637.cc:9:38: note: read of non-const variable 'asize' is not allowed in a constant expression
ex1637.cc:9:14: note: declared here
unsigned int asize = 255; Array<int, asize> a2;
             ^
1 error generated.
```

(d) is invalid, the compiler complaints:

```bash
ex1637.cc:10:41: error: conversion from 'const double' to 'int' is not allowed in a converted constant expression
const double db = 3.1415; Array<double, db> a3;
                                        ^~
1 error generated.
```
