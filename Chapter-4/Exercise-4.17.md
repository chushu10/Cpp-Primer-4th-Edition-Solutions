# Exercise 4.17

Given that `p1` and `p2` point to elements in the same array, what does the following statement do?

`p2 += p2 - p1;`

Are there any values of `p1` or `p2` that could make this code illegal?

**Answer**:

`p2 += p2 - p1;` first calculates the difference between `p2` and `p1` say `diff`, then add that difference to `p2` so that `p2` points to element `diff` away from the current element.

Remind that `diff` can be positive or negative, so that if adding `p2` and `diff` makes `p2` points to the element ahead of the first element of the array or more than one past the last element of the array, it will be illegal. See example below:

```cpp
int arr[] = {1, 2, 3, 4, 5};
int *p2 = &arr[1];
int *p1 = &arr[4];
p2 += p2 - p1; // p2 - p1 is -3, then p2 will point to arr[-2], which is illegal. However, you can still dereference p2, but only to get a garbage value.
```