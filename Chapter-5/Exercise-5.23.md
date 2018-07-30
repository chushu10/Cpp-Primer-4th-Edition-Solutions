# Exercise 5.23

Predict the output of the following program and explain your reasoning. Now run the program. Is the output what you expected? If not, figure out why.

```cpp
int x[10];
int *p = x;
cout << sizeof(x)/sizeof(*x) << endl;
cout << sizeof(p)/sizeof(*p) << endl;
```

**Answer**:

`sizeof(x)/sizeof(*x)` = 10, because the `sizeof` operator on array `x` is the size of the entire array; `sizeof(p)/sizeof(*p)` = 1, because `p` is only a pointer point to `int` type, we cannot assume that it will point to an array, so `sizeof(p)` yields the size to hold a pointer which is exactly the size to hold an `int`.