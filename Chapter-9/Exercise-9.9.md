# Exercise 9.9

Write a loop to write the elements of a `list` in reverse order.


**Answer**:

```cpp
list<int> lst1;
list<int>::iterator iter1 = lst1.begin(), iter2 = lst1.end();
while (iter1 != iter2) {
    cout << *(--iter2) << endl;
}
```