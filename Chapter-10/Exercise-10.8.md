# Exercise 10.8

Write an expression using a `map` iterator to assign a value to an element.

**Answer**:

```cpp
map<string, int>::iterator map_it = word_count.begin();
map_it->second = 5;
```