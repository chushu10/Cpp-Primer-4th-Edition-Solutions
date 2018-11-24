# Exercise 12.31

The data members of pair are public, yet this code doesn't compile. Why?

```cpp
pair<int, int> p2 = {0, 42}; // doesn't compile, why?
```

**Answer**:

The correct version is `pair<int, int> p2(0, 42)`. Because `pair` do provide a constructor, so we can't use a initializer like the code above.