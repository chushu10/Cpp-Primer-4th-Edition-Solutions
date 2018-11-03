# Exercise 11.6

Using `fill_n` , write a program to set a sequence of `int` values to 0.

**Answer**:

```cpp
vector<int> ivec;
fill_n(back_inserter(ivec), 10, 0);
```