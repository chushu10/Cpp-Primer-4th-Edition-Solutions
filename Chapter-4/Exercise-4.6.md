# Exercise 4.6

This code fragment intends to assign the value of its index to each array element. It contains a number of indexing errors. Identify them.

```cpp
const size_t array_size = 10;
int ia[array_size];
for (size_t ix = 1; ix <= array_size; ++ix)
    ia[ix] = ix;
```

**Answer**:

The index should be 0 to 9 in an array of 10 elements, so the code should be:

```cpp
const size_t array_size = 10;
int ia[array_size];
for (size_t ix = 0; ix < array_size; ++ix)
    ia[ix] = ix;
```