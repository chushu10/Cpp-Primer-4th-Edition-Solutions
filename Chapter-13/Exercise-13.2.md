# Exercise 13.2

The second initialization below fails to compile. What can we infer about the definition of `vector`?

```cpp
[View full width]
vector<int> v1(42); // ok: 42 elements, each 0
vector<int> v2 = 42; // error: what does this error tell us
about vector?
```

**Answer**:

The `vector<int>` class has no constructor that takes an `int` as argument and that constructor is not `explicit`. We should explicitly invoke the constructor of `vector<int>`:

```cpp
std::vector<int> v2 = std::vector<int>(42);
```