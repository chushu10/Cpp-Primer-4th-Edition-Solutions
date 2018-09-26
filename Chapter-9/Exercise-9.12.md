# Exercise 9.12

Write a function that takes a pair of iterators and an `int` value. Look for that value in the range and return a bool indicating whether it was found.

**Answer**:

```cpp
bool isElemInRange(vector<int>::const_iterator first,
                   vector<int>::const_iterator last,
                   int elem)
{
    while (first != last) {
        if (*first++ == elem) {
            return true;
        }
    }
    return false;
}
```