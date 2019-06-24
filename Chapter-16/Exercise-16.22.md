# Exercise 16.22

Given the following templates

```cpp
template <class Type>
Type calc(const Type* array, int size);

template <class Type>
Type fcn(Type p1,Type p2);
```

which ones of the following calls, if any, are errors? Why?

```cpp
double dobj;
float fobj;
char cobj;
int ai[5] = { 511, 16, 8, 63, 34 };

(a) calc(cobj, 'c');
(b) calc(dobj, fobj);
(c) fcn(ai, cobj);
```

**Answer**:

All of them are errors:

- For (a) and (b), their first parameters must be pointers.
- For (c), its parameters must be the same type.
