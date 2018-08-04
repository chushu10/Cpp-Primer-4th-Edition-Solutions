# Exercise 5.33

Given the following set of definitions:

```cpp
int ival;
double dval;
const string *ps;
char *pc;
void *pv;
```

rewrite each of the following using a named cast notation:

(a) `pv = (void*)ps;`
(b) `ival = int(*pc);`
(c) `pv = &dval;`
(d) `pc = (char*) pv;`

**Answer**:

(a) `pv = const_cast<void*>ps;`
(b) `ival = reinterpret_cast<int>(*pc);`
(c) `pv = static_cast<void*>&dval;`
(d) `pc = dynamic_cast<char*> pv;`