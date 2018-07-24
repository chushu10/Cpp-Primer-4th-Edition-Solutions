# Exercise 5.6

Explain the behavior of the following `while` condition.

```cpp
char *cp = "Hello World";
while (cp && *cp)
```

**Answer**:

It will judge whether `cp` is not NULL first, then judge whether the first element is not 0. If both expressions turn out to be `true`, then the body of `while` can be executed.