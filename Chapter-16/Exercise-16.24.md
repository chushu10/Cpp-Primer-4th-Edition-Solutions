# Exercise 16.24

In Section 16.2.1 (p. 638 ) we saw that the arguments to the version of `compare` that has a single template type parameter must match exactly. If we wanted to call the function with compatible types, such as `int` and `short` , we could use an explicit template argument to specify either `int` or `short` as the parameter type. Write a program that uses the version of `compare` that has one template parameter. Call `compare` using an explicit template argument that will let you pass arguments of type `int` and `short`.

**Answer**:

```cpp
#include <iostream>
using namespace std;

template <typename T>
int compare(const T &v1, const T &v2)
{
    if (v1 < v2) return -1;
    if (v2 < v1) return 1;
    return 0;
}

int main()
{
    int ival = 10;
    short shval = 20;
    cout << compare(static_cast<short>(ival), shval) << endl;
    return 0;
}
```
