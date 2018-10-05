# Exercise 9.19

Assuming `iv` is a `vector` of `int`s, what is wrong with the following program? How might you correct the problem(s)?

```cpp
vector<int>::iterator mid = iv.begin() + iv.size()/2;
while (vector<int>::iterator iter != mid)
    if (iter == some_val)
        iv.insert(iter, 2 * some_val);
```

**Answer**:

1. `iter` is uninitialized when comparing to `mid` in the `while` statement.
2. Insertion will invalidate the cached iterator `mid`, since the size of `iv` will be incremented by 1 after each insertion. Instead, recalculate `mid` each time in the `while` statement:

```cpp
vector<int>::iterator iter = some_val;
while (iter != iv.begin() + iv.size()/2)
    if (iter == some_val)
        iv.insert(iter, 2 * some_val);
```