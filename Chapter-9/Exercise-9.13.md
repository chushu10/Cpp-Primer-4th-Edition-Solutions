# Exercise 9.13

Rewrite the program that finds a value to return an iterator that refers to the element. Be sure your function works correctly if the element does not exist.

**Answer**:

```cpp
/*
 * Return an iterator that refers to the element found.
 * Return an iterator that refers to one past the last
 * element if not found
 */
vector<int>::iterator
findElemInRange(vector<int>::iterator first,
                vector<int>::iterator last,
                int elem)
{
    while (first != last) {
        if (*first++ == elem) {
            return --first;
        }
    }
    return last;
}
```