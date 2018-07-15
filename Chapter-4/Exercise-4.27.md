# Exercise 4.27

Given the following `new` expression, how would you `delete pa`?

```cpp
int *pa = new int[10];
```

**Answer**:

```cpp
delete [] pa;
```