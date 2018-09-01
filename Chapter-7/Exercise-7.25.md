# Exercise 7.25

Given the following function declarations and calls, which, if any, of the calls are illegal? Why? Which, if any, are legal but unlikely to match the programmer's intent? Why?

```cpp
// declarations
char *init(int ht, int wd = 80, char bckgrnd = ' ');
```

(a) `init();`
(b) `init(24, 10);`
(c) `init(14, '*');`

**Answer**:

(a) is illegal, because `ht` has no default argument, you have to specify it.
(b) is legal.
(c) is legal but unlikely to match the programmer's intent, because '*' is also an `int` type.