# Exercise 4.9

Write a program to define an array of 10 `int`s. Give each element the same value as its position in the array.

**Answer**:

```cpp
const size_t arraySize = 10;
int ia[arraySize];
for (size_t i = 0; i < arraySize; ++i) {
    ia[i] = i;
}
```