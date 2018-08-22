# Exercise 7.2

Indicate which of the following functions are in error and why. Suggest how you might correct the problems.

(a)

```cpp
int f() {
    string s;
    // ...
    return s;
}
```

(b) `f2(int i) { /* ... */ }`
(c) `int calc(int v1, int v1) /* ... */ }`
(d) `double square(double x) return x * x;`

**Answer**:

(a) The function's return type is different from the type of the variable it returns.
(b) The return type must be defined.
(c) Cannot define parameters with the same name; lack of open curly brace.
(d) Must have open and close curly braces.
