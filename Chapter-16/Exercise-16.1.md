# Exercise 16.1

Write a template that returns the absolute value of its parameter. Call the template on values of at least three different types. Note: until we discuss how the compiler handles template instantiation in Section 16.3 (p. 643 ), you should put each template definition and all uses of that template in the same file.

**Answer**:

```cpp
#include <iostream>
using namespace std;

template <typename T> T abs(const T& a)
{
    return a > 0 ? a : 0 - a;
}

int main()
{
    double a = -0.111;
    char b = '1';
    int c = -1;
    cout << abs(a) << endl;
    cout << abs(c) << endl;
    cout << abs(b) << endl;
    return 0;
}
```
