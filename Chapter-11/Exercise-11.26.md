# Exercise 11.26

Explain why each of the following is incorrect. Identify which errors should be caught during compilation.

(a)

```cpp
string sa[10];
const vector<string> file_names(sa, sa+6);
vector<string>::iterator it = file_names.begin()+2;
```

(b)

```cpp
const vector<int> ivec;
fill(ivec.begin(), ivec.end(), ival);
```

(c)

```cpp
sort(ivec.begin(), ivec.rend());
```


(d)

```cpp
sort(ivec1.begin(), ivec2.end());
```

**Answer**:

(a) The iterator returned by `file_names.begin()` is a `const` iterator.

(b) `fill` requires its third parameter to be writable.

(c) `sort` requires both its first and second parameters to be writable.

(d) `sort` requires its parameters be iterators point to the same container.