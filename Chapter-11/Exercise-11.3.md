# Exercise 11.3

Use `accumulate` to sum the elements in a `vector<int>`.

**Answer**:

```cpp
vector<int> ivec;
// add elements
int sum = accumulate(ivec.begin(), ivec.end(), 0);
```