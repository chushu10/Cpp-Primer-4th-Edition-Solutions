# Exercise 7.37

Given the declarations for `f`, determine whether the following calls are legal. For each call list the viable functions, if any. If the call is illegal, indicate whether there is no match or why the call is ambiguous. If the call is legal, indicate which function is the best match.

```cpp
void f();
void f(int);
void f(int, int);
void f(double, double = 3.14);
```

(a) `f(2.56, 42);`
(b) `f(42);`
(c) `f(42, 0);`
(d) `f(2.56, 3.14);`

**Answer**:

(a) ambiguous, because both `void f(int, int)` and `void f(double, double = 3.14)` are viable functions, and no one is better than the other.
(b) `void f(int)` is the only viable function, and the best match.
(c) `void f(int, int)` and `void f(double, double = 3.14)` are viable functions, and `void f(int, int)` is the best match(doesn't need conversion, perfect match).
(d) `void f(int, int)` and `void f(double, double = 3.14)` are viable functions, and `void f(double, double = 3.14)` is the best match(doesn't need conversion, perfect match).
