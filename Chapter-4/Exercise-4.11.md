# Exercise 4.11

Explain each of the following definitions. Indicate whether any are illegal and if so why.

(a) `int* ip;`
(b) `string s, *sp = 0;`
(c) `int i; double* dp = &i;`
(d) `int* ip, ip2;`
(e) `const int i = 0, *p = i;`
(f) `string *p = NULL;`

**Answer**:

(a) is legal, but a misleading declaration, and you should always initialize a pointer.
(b) is legal.
(c) is **illegal**, because `dp` is a pointer points to double type, it cannot point to `int` object `i`. Again, declaring pointer with * near the type is a bad practice.
(d) is legal, but a misleading one.
(e) is legal, but my compiler will generate a **warning**:

```bash
ex411.cc:3:27: warning: expression which evaluates to zero treated as a null pointer constant of type 'const int *'
      [-Wnon-literal-null-conversion]
    const int i = 0, *p = i;
                          ^
1 warning generated.
```

So I suppose it is not a good practice, use preprocessor variable `NULL` instead.

(f) is legal.