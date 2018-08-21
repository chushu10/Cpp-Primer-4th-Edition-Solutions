# Exercise 6.27

Explain this loop:

```cpp
string s;
while (cin >> s && s != sought) { } // empty body
assert(cin);
// process s
```

**Answer**:

It's impossible that `cin` will be 0.