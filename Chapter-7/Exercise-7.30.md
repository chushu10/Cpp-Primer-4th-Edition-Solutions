# Exercise 7.30

Rewrite the `isShorter` function from page 235 as an `inline` function.

**Answer**:

```cpp
inline bool isShorter(const string &s1, const string &s2)
{
    return s1.size() < s2.size();
}
```