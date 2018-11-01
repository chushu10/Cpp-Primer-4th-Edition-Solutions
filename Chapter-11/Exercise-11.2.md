# Exercise 11.2

Repeat the previous program, but read values into a list of `string`s.

**Answer**:

```cpp
vector<string> ivec;
ivec.push_back("1");
ivec.push_back("0");
ivec.push_back("0");
ivec.push_back("8");
ivec.push_back("6");
cout << count(ivec.begin(), ivec.end(), "0") << endl; // 2
```