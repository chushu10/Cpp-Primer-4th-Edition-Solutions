# Exercise 2.22

The following program fragment, while legal, is an example of poor style. What problem(s) does it contain? How would you improve it?

```cpp
for (int i = 0; i < 100; ++i)
    // process i
```

**Answer**: Number `100` is a magic number, we should initialize a meaningful variable instead.

```cpp
int bufSize = 100; // suppose we loop through a buffer
for (int i = 0; i < bufSize; ++i)
    // process i
```