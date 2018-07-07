# Exercise 4.14

Write code to change the value of a pointer. Write code to change the value to which the pointer points.

**Answer**:

```cpp
int i = 10;
int j = 11;
int *p = &i;
p = &j; // change the value of pointer
*p = 12; // change the value to which the pointer points, now j should be 12
```