# Exercise 9.25

What happens in the program that erased a range of elements if `val1` is equal to `val2`. What happens if either `val1` or `val2` or both are not present.

**Answer**:

Suppose you use the code below to erase a range of elements from a list(**IMPORTANT!**):

```cpp
list<string> slist;
// populate some strings to slist
list<string>::iterator elem1, elem2;
elem1 = find(slist.begin(), slist.end(), val1);
elem2 = find(slist.begin(), slist.end(), val2);
slist.erase(elem1, elem2);
```

1. If `val1` is equal to `val2`, then nothing is erased.
2. If only `val1` is not present, then `elem1` points to one past the last element of `slist`, then nothing is erased.
3. If only `val2` is not present, then `elem2` points to one past the last element of `slist`, then `slist` is erased from `elem1` to the end.
4. If both `val1` and `val2` are not present, that means both `val1` and `val2` point to one past the last element of `slist`, then nothing is erased.