# Exercise 7.28

Write a function that returns 0 when it is first called then generates numbers in sequence each time it is called again.

**Answer**:

```cpp
int generate()
{
    static int num = 0;
    return num++;
}
```