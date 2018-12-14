# Exercise 14.4

Both the `string` and `vector` types define an overloaded `==` that can be used to compare objects of those types. Identify which version of `==` is applied in each of the following expressions:

```cpp
string s; vector<string> svec1, svec2;
"cobble" == "stone"
svec1[0] == svec2[0];
svec1 == svec2
```

**Answer**:

```cpp
string s; vector<string> svec1, svec2;
"cobble" == "stone"   // string ==
svec1[0] == svec2[0]; // string ==
svec1 == svec2        // vector ==
```