# Exercise 9.18

Write a program to copy elements from a `list` of `int`s into two `deque`s. The `list` elements that are even should go into one `deque` and those that are odd into the second.

**Answer**:

```cpp
list<int> ilist;
// add some elements to ilist...
list<int>::const_iterator it = ilist.begin();
for ( ; it != ilist.end(); ++it) {
    if (*it % 2 == 0) {
        even_deque.push_back(*it);
    } else {
        odd_deque.push_back(*it);
    }
}
```