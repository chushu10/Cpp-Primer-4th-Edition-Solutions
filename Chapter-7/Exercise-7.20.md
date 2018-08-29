# Exercise 7.20

Rewrite `factorial` as an iterative function.

**Answer**:

```cpp
int factorial(int val) {
    int result = 1;
    for (int i = val; i > 1; --i) {
        result *= i;
    }
    return result;
}
```