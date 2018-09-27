# Exercise 9.16

What type should be used as the index into a `vector` of `int`s?

**Answer**:

`vector<int>::size_type`

Example:

```cpp
vector<int> ivec;
// ...
for (vector<int>::size_type i = 0; i != ivec.size(); ++i) {
    cout << ivec[i] << endl;
}
```