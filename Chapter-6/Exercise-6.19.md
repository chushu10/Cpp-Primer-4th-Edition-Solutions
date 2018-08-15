# Exercise 6.19

The first program in this section could be written more succinctly. In fact, its action could be contained entirely in the condition in the `while`. Rewrite the loop so that it has an empty body and does the work of finding the element int the condition.

**Answer**:

```cpp
// Before
vector<int>::iterator iter = vec.begin();
while (iter != vec.end()) {
    if (value == *iter)
        break; // ok: found it!
    else
        ++iter; // not found: keep looking
}
if (iter != vec.end()) // break to here
    // continue processing
```

```cpp
// After
vector<int>::iterator iter = vec.begin();
while (iter != vec.end()) {
    if (value == *iter++)
        break; // ok: found it!
}
```