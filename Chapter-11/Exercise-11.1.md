# Exercise 11.1

The algorithm header defines a function named `count` that is similar to `find`. It takes a pair of iterators and a value and returns a count of how often that value appears. Read a sequence of `int`s into a `vector`. Count how many elements have a given value.

**Answer**:

```cpp
vector<int> ivec;
ivec.push_back(1);
ivec.push_back(0);
ivec.push_back(0);
ivec.push_back(8);
ivec.push_back(6);
cout << count(ivec.begin(), ivec.end(), 0) << endl; // 2
```