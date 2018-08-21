# Exercise 6.26

What happens in the following loop:

```cpp
string s;
while (cin >> s) {
    assert(cin);
    // process s
}
```

**Answer**:

The program will terminate at the `assert` macro if we input EOF.