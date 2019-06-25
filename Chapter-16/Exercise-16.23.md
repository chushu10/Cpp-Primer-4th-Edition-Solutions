# Exercise 16.23

The library `max` function takes a single type parameter. Could you call `max` passing it an `int` and a `double` ? If so, how? If not, why not?

**Answer**:

By specify explicit template argument:

```cpp
#include <iostream>     // std::cout
#include <algorithm>    // std::max
using namespace std;

int main()
{
    int ival = 10;
    double dval = 20.2;
    cout << max<double>(ival, dval) << endl;
    cout << max<int>(ival, dval) << endl;
    return 0;
}
```
