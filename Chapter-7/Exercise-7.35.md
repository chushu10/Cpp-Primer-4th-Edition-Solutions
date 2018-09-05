# Exercise 7.35

Explain the effect of the second declaration in each one of the following sets of declarations. Indicate which, if any, are illegal.

(a)

```cpp
int calc(int, int);
int calc(const int, const int);
```

(b)

```cpp
int get();
double get();
```

(c)

```cpp
int *reset(int *);
double *reset(double *);
```

**Answer**:

(a) The second declaration is treated as a re-declaration of the first. Because a difference in whether the parameters are `const` or not has no effect on the objects that cna be passed to the function. However, a re-declaration is legal.

(b) It is illegal, because only return type is different.

(c) The second declaration is treated as the overload of the first one. Because they have different parameter list.