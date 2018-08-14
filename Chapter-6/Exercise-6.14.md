# Exercise 6.14

Explain each of the following loops. Correct any problems you detect.

(a)

```cpp
for (int *ptr = &ia, ix = 0;
      ix != size && ptr != ia+size;
      ++ix, ++ptr) { /* ... */ }
```

(b)

```cpp
for (; ;) {
    if (some_condition) return;
    // ...
}
```

(c)

```cpp
for (int ix = 0; ix != sz; ++ix) { /* ... */ }
if (ix != sz)
    // ...
```

(d)

```cpp
int ix;
for (ix != sz; ++ix) { /* ... */ }
```

(e)

```cpp
for (int ix = 0; ix != sz; ++ix, ++sz) { /* ... */ }
```

**Answer**:

(a) Initialize `ptr` to the address of `ia`,  and `ix` to 0. Loop through `&ia` to `&ia + size`, so the correct version should be:

```cpp
for (int *ptr = &ia, ix = 0;
      ix != size && ptr != &ia+size;
      ++ix, ++ptr) { /* ... */ }
```

(b) Loop forever until the program meets some condition.

(c) `ix` cannot be seen outside of the for loop, correct version:

```cpp
for (int ix = 0; ix != sz; ++ix) { /* ... */ }
// When get here, ix should be not equal with sz, so just do it
    // ...
```

(d) Lack of the null init-statement, and `ix` should be initialized. Correct version:

```cpp
int ix = 0; // init ix
for (/* null */;ix != sz; ++ix) { /* ... */ }
```

(e) `sz` shouldn't be incremented, otherwise the loop will be executed forever. Correct version:

```cpp
for (int ix = 0; ix != sz; ++ix) { /* ... */ }
```