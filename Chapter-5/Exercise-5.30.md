# Exercise 5.30

Which of the following, if any, are illegal or in error?

(a) `vector<string> svec(10);`
(b) `vector<string> *pvec1 = new vector<string>(10);`
(c) `vector<string> **pvec2 = new vector<string>[10];`
(d) `vector<string> *pv1 = &svec;`
(e) `vector<string> *pv2 = pvec1;`
(f) `delete svec;`
(g) `delete pvec1;`
(h) `delete [] pvec2;`
(i) `delete pv1;`
(j) `delete pv2;`

**Answer**:

(a) is legal;
(b) is legal;
(c) is illegal, because `vector<string>[]` is type `vector<sting> *`, it cannot be used to allocate memory for a different type which is `vector<string> **`;
(d) is legal;
(e) is legal;
(f) is illegal, because `svec` is not dynamically allocated by `new`;
(g) is legal;
(h) is legal if (c) is corrected as `vector<string> *pvec2 = new vector<string>[10];`
(i) is in error, because `pv1` points to a local memory which is created by defining `vector<string> svec(10);`
(j) is legal, but error-prone. If we happened to release `pvec1` in prior, releasing `pv2` will  result in serious issue.