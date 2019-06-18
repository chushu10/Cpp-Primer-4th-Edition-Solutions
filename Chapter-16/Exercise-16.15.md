# Exercise 16.15

Write a function template that can determine the size of an array.

**Answer**:

```cpp
#include <iostream>
using namespace std;

template <class T, size_t N>
size_t array_size(T (&parm)[N])
{
    if (parm == NULL) return 0;
    return N;
}

int main()
{
    int arr[10];
    double darr[55];
    cout << array_size(arr) << endl;
    cout << array_size(darr) << endl;
    return 0;
}
```
