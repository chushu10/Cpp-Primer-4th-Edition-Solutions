# Exercise 4.13

Why is the first pointer initialization legal and the second illegal?

```cpp
int i = 42;
void *p = &i;
long *lp = &i;
```

**Answer**:

`p` is a `void *` pointer, which can point to any type of object; `lp` can only point to `long` object.