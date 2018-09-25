# Exercise 9.10

Which, if any, of the following iterator uses are in error?

```cpp
const vector< int > ivec(10);
vector< string > svec(10);
list< int > ilist(10);

(a) vector<int>::iterator         it = ivec.begin();
(b) list<int>::iterator           it = ilist.begin()+2;
(c) vector<string>::iterator      it = &svec[0];
(d) for (vector<string>::iterator it = svec.begin(); it != 0; ++it) // ...
```

**Answer**:

(a) is in error, should be `vector<int>::const_iterator it = ivec.begin();`.
(b) is in error, because the `list` iterator does not support the arithmetic operations addition or subtraction nor does it support the relational (`<=`, `<`, `>=`, `>`) operators.
(c) is in error, should be `string *pStr = &svec[0];`
(d) is in error, should be `for (vector<string>::iterator it = svec.begin(); it != svec.end(); ++it)`