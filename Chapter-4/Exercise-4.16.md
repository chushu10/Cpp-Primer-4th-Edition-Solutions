# Exercise 4.16

What does the following program do?

```cpp
int i = 42, j = 1024;
int *p1 = &i, *p2 = &j;
*p2 = *p1 * *p2;
*p1 *= *p1;
```

**Answer**:

```cpp
int i = 42, j = 1024;
int *p1 = &i, *p2 = &j; // declaring p1 points to i, and p2 points to j
*p2 = *p1 * *p2; // change the value of j to be i * j, which is 42 * 1024 = 43008
*p1 *= *p1; // change the value of i to be i * i, which is 42 * 42 = 1764
```