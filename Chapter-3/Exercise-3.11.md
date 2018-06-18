# Exercise 3.11

Which, if any, of the following vector definitions are in error?

(a) `vector< vector<int> > ivec;`
(b) `vector<string> svec = ivec;`
(c) `vector<string> svec(10, "null");`

**Answer**: (b) is in error, because `svec` holds `string` type, while `ivec` holds `vector<int>` type. Others are valid.