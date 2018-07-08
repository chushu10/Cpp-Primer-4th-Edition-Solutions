# Exercise 4.21

Based on the definitions in the [previous exercise](Exercise-4.20.md), which of the following assignments are legal? Explain why.

(a) `i = ic;`
(b) `pic = &ic;`
(c) `cpi = pic;`
(d) `pic = cpic;`
(e) `cpic = &ic;`
(f) `ic = *cpic;`

**Answer**:

(a) is legal, you can change the value of a non-`const` variable;
(b) is legal, because `pic` itself is a non-`const` pointer, you can change the address it points to;
(c) is **illegal** because the existence of `cpi` itself is illegal;
(d) is legal, please reference (b);
(e) is **illegal**, because `cpic` itself is a `const` pointer, you can't change the address it points to, even if you assign the same value to it;

```bash
error: cannot assign to variable 'cpic' with const-qualified type 'const int *const'
    cpic = &ic;
    ~~~~ ^
ex420.cc:6:22: note: variable 'cpic' declared const here
    const int *const cpic = &ic;
    ~~~~~~~~~~~~~~~~~^~~~~~~~~~
1 error generated.
```

(f) is **illegal**, because `ic` is a `const` object, you can't change it value, that simple:

```bash
error: cannot assign to variable 'ic' with const-qualified type 'const int'
    ic = *cpic;
    ~~ ^
ex420.cc:4:15: note: variable 'ic' declared const here
    const int ic = i;
    ~~~~~~~~~~^~~~~~
2 errors generated.
```