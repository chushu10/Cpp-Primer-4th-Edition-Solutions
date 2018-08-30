# Exercise 7.23

Given the following declarations, determine which calls are legal and which are illegal. For those that are illegal, explain why.

```cpp
double calc(double);
int count(const string &, char);
int sum(vector<int>::iterator, vector<int>::iterator, int);
vector<int> vec(10);
```

(a) `calc(23.4, 55.1);`
(b) `count("abcda", 'a');`
(c) `calc(66);`
(d) `sum(vec.begin(), vec.end(), 3.8);`

**Answer**:

(a) illegal, `calc` has only one parameter.
(b) legal, parameters match and "abcda" is a const literal so that it can be the argument of `const string &` type.
(c) legal.
(d) illegal, last parameter not match.