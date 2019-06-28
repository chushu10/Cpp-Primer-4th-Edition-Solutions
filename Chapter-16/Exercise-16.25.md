# Exercise 16.25

Use an explicit template argument to make it sensible to call `compare` passing two `string` literals.

**Answer**:

```cpp
#include <iostream>
#include <string>
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
    const string a = "Hello";
    const string b = "World";
    cout << compare<string>(a, b) << endl;
    cout << compare<string>(b, a) << endl;
    return 0;
}
```
