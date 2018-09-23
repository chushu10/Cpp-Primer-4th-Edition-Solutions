# Exercise 9.1

Explain the following initializations. Indicate if any are in error, and if so, why.

```cpp
int ia[7] = { 0, 1, 1, 2, 3, 5, 8 };
string sa[6] = {
"Fort Sumter", "Manassas", "Perryville",
"Vicksburg", "Meridian", "Chancellorsville" };
(a) vector<string> svec(sa, sa+6);
(b) list<int> ilist( ia+4, ia+6);
(c) vector<int> ivec(ia, ia+8);
(d) list<string> slist(sa+6, sa);
```

**Answer**:

(a) is right, the iterators in the constructor mark the first and one past the last element to be copied.
(b) is right, same reason as (a).
(c) is in error, because the second iterator marks two past the last element, which will result in undefined value of tha last element of `ivec`.
(d) is in error, the program will crash since we specify the iterators reversely. The first iterator should denotes element ahead of the element denoted by the second element.