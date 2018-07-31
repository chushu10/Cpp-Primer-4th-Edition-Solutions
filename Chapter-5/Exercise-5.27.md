# Exercise 5.27

The following expression fails to compile due to operator precedence. Using Table 5.4(p. 170), explain why it fails. How would you fix it?

```cpp
string s = "word";
// add an 's' to the end, if the word doesn't already end in 's'
string p1 = s + s[s.size() - 1] == 's' ? "" : "s";
```

**Answer**:

```cpp
string s = "word";
// add an 's' to the end, if the word doesn't already end in 's'
string p1 = s + (s[s.size() - 1] == 's' ? "" : "s");
```