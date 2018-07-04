# Exercise 4.3

Which, if any, of the following definitions are in error?

(a) `int ia[7] = { 0, 1, 1, 2, 3, 5, 8 };`
(b) `vector<int> ivec = { 0, 1, 1, 2, 3, 5, 8 };`
(c) `int ia2[] = ia1;`
(d) `int ia3[] = ivec;`

**Answer**:

(a) is ok, we can initialize an array with elements in braces, the number of elements in braces is less or equal than the dimension of `ia`;
(b) is ok, we can initialize a `vector` with elements in braces;
(c) is in error, because we can't initialize an array with another one;
(d) is in error, because we can't initialize an array with a `vector`.