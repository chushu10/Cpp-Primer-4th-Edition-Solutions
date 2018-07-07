# Exercise 4.18

Write a program that uses pointers to set the elements in an array of `int`s to zero.

**Answer**:

```cpp
const size_t arrSize = 5;
int arr[arrSize];
for (int *pbeg = arr, *pend = arr + arrSize;
            pbeg != pend; ++pbeg) {
    *pbeg = 0;
}
```