# Exercise 7.18

What potential run-time problem does the following function have?

```cpp
string &processText() {
    string text;
    while (cin >> text) { /* ... */ }
    // ...
    return text;
}
```

**Answer**:

It returns a reference to local object `text`, should be:

```cpp
string processText() { // do not return reference
    string text;
    while (cin >> text) { /* ... */ }
    // ...
    return text; // return copy of the local object text
}
```