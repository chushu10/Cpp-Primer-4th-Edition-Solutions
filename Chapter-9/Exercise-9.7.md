# Exercise 9.7

What is wrong with the following program? How might you correct it?

```cpp
list<int> lst1;
list<int>::iterator iter1 = lst1.begin(), iter2 = lst1.end();
while (iter1 < iter2) /* . . . */
```

**Answer**:

The list iterator does not support the relational (`<=`, `<`, `>=`, `>`) operators.

Correction:

```cpp
list<int> lst1;
list<int>::iterator iter1 = lst1.begin(), iter2 = lst1.end();
while (iter1 < iter2) {
    // do something...
    iter1++;
}
```