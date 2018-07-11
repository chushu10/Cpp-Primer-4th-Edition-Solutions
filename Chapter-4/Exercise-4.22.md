# Exercise 4.22

Explain the difference between the following two `while` loops:

```cpp
const char *cp = "hello";
int cnt;
while (cp) { ++cnt; ++cp; }
while (*cp) { ++cnt; ++cp; }
```

**Answer**:

- The first loop `while (cp) { ++cnt; ++cp; }` will loop forever, because `while` only judge whether `cp` isn't a `NULL` value;
- The second loop `while (*cp) { ++cnt; ++cp; }` will end as expected, with `cnt` equals 5, because `while` judges whether `*cp` is a `NULL` terminator. Since `cp` is a C-style `string` literal, it will always has a `NULL` terminator at the end of the `string` array.