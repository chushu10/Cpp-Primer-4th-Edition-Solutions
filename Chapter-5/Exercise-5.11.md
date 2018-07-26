# Exercise 5.11

What are the values of `i` and `d` after the each assignment:

```cpp
int i;
double d;
d = i = 3.5;
i = d = 3.5;
```

**Answer**:

```cpp
int i;
double d;
d = i = 3.5; // i = 3, d = 3.0
i = d = 3.5; // i = 3, d = 3.5
```