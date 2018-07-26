# Exercise 5.12

Explain what happens in each of the `if` tests:

```cpp
if (42 = i) // . . .
if (i = 42) // . . .
```

**Answer**:

```cpp
if (42 = i) // compile error
if (i = 42) // always true, and i is assigned to 42
```