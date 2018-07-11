# Exercise 4.23

What does the following program do?

```cpp
const char ca[] = {'h', 'e', 'l', 'l', 'o'};
const char *cp = ca;
while (*cp) {
    cout << *cp << endl;
    ++cp;
}
```

**Answer**:

You should not rely on the behavior of this program. Since char array `ca` does not contain a null terminator, it is not guaranteed that the `while` loop will end as expected.