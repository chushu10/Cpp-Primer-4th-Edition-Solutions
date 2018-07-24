# Exercise 5.2

Determine the result of the following expressions and indicate which results, if any, ar machine-dependent.

```cpp
-30 * 3 + 21 / 5
-30 + 3 * 21 / 5
30 / 3 * 21 % 5
-30 / 3 * 21 % 4
```

**Answer**:

```cpp
-30 * 3 + 21 / 5 = -86
-30 + 3 * 21 / 5 = -18
30 / 3 * 21 % 5 = 0
-30 / 3 * 21 % 4 = (machine-dependent) probably -2
```