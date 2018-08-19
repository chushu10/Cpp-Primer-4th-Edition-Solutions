# Exercise 6.22

The last example in this section that jumped back to `begin` could be better written using a loop. Rewrite the code to eliminate the `goto`.

**Answer**:

```cpp
// before
begin:
    int sz = get_size();
    if (sz <= 0) {
        goto begin;
    }
```

```cpp
// after
int sz = get_size();
while (sz <= 0) {
    sz = get_size();
}
```