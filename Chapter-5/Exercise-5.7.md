# Exercise 5.7

Write the condition for a `while` loop that would read `int`s from the standard input and stop when the value read is equal to 42.

**Answer**:

```cpp
int input;
while(cin >> input && input != 42) {
    // do something
}
```