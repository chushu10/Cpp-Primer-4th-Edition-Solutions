# Exercise 2.19

What is the value of `j` in the following program?

```cpp
int i = 42;

int main()
{
    int i = 100;
    int j = i;
    // ...
}
```

**Answer**: The value of `j` is 100, because the local `i` hides the definition of global `i`.