# Exercise 11.28

Assume `lst` is a container that holds 100 elements. Explain the following program fragment and fix any bugs you think are present.

```cpp
vector<int> vec1;
reverse_copy(lst.begin(), lst.end(), vec1.begin());
```

**Answer**:

`vec1` is an empty `vector`, while `reverse_copy` assumes that the size of `vec1` is at least as large as `lst`. In this example, we should use `back_inserter` iterator to replace `vec1.begin()`, otherwise the program will crash.

```cpp
vector<int> vec1;
reverse_copy(lst.begin(), lst.end(), back_inserter(vec1);
```