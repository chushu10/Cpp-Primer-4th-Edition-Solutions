# Exercise 5.13

The following assignment is illegal. Why? How would you correct it?

```cpp
double dval;
int ival;
int *pi;
dval = ival = pi = 0;
```

**Answer**:

Because pointer `pi` cannot be assigned to `int` type `ival`, I would correct it as:

```cpp
pi = 0;
ival = dval = 0;
```