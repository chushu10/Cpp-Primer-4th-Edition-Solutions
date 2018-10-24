# Exercise 10.16

Define and initialize a variable to hold the result of a call to `find` on a `map` from `string` to `vector` of `int`.

**Anwer**:

```cpp
map<string, vector<int> > test_map;
string key;
map<string, vector<int> >::iterator it = test_map.find(key);
```