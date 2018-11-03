# Exercise 11.7

Determine if there are any errors in the following programs and, if so, correct the error(s):

(a)
```cpp
vector<int> vec;
list<int> lst;
int i;
while (cin >> i)
    lst.push_back(i);
copy(lst.begin(), lst.end(), vec.begin());
```

(b)
```cpp
vector<int> vec;
vec.reserve(10);
fill_n(vec.begin(), 10, 0);
```

**Answer**:

(a) the last sentence should be:
`copy(lst.begin(), lst.end(), back_inserter(vec);`

(b) the `reserve` function only increase the capacity of the `vector`, we should use `back_iterator`:
`fill_n(back_inserter(vec), 10, 0);`
