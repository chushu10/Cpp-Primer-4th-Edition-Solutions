# Exercise 4.20

Which of the following initialization are legal? Explain why.

(a) `int i = -1;`
(b) `const int ic = i;`
(c) `const int *pic = &ic;`
(d) `int *const cpi = &ic;`
(e) `const int *const cpic = &ic;`

**Answer**:

(a) is legal, can't find the reason not to do so;
(b) is legal, we should initialize a `const` object when defining it, otherwise, we will get a compile error;
(c) is legal, `pic` is a pointer that thinks it points to a `const` object, it doesn't matter that the object it points to is `const` or not;
(d) is **illegal**, while `cpi` itself is a `const`, it actually is a plain pointer, so that assigning the address of a `const` object `ic` to `cpi` is a compile-time error, as can be seen below:

```bash
error: cannot initialize a variable of type 'int *const' with an rvalue of type 'const int *'
    int *const cpi = &ic;
               ^     ~~~
1 error generated.
```

(e) is legal, because `cpic` is a `const` pointer, so it can hold the address of a `const` object.