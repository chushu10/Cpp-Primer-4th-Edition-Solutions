# Exercise 7.5

Write a function that takes an `int` and a pointer to an `int` and returns the larger of the `int` value of the value to which the pointer points. What type should you use for the pointer?

**Answer**:

```cpp
int larger(int ival, int *pi) {
    return ival > *pi ? ival : *pi;
}
```