# Exercise 7.39

Explain the effect of the second declaration in each one of the following sets of declarations. Indicate which, if any, are illegal.

(a)

```cpp
int calc(int, int);
int calc(const int&, const int&);
```

(b)

```cpp
int calc(char*, char*);
int calc(const char*, const char*);
```

(c)

```cpp
int calc(char*, char*);
int calc(char* const, char* const);
```

**Answer**:

(a) Overload, because we can overload a function based on whether a reference parameter refers to a `const` or non`const` type.
(b) Overload, because we can overload a function based on whether a pointer points to a `const` or non`const` object.
(c) illegal, because whether the pointer itself is `const` or not cannot make the function an overloaded function.