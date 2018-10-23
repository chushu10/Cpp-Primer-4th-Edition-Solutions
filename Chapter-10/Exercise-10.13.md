# Exercise 10.13

Given a `map<string, vector<int> >`, write the types used as an argument and as the return value for the version of `insert` that inserts one element.

**Answer**:

```cpp
pair< map<string, vector<int> >::iterator, bool> ret;
```