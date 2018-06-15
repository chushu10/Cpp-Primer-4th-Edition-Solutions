# Exercise 3.1

Rewrite the program from Section 2.3(p. 43) that calculated the result of raising a given number to a given power to use appropriate `using` declarations rather than accessing library names through a `std::` prefix.

**Answer**:

```cpp
#include <iostream>
using std::cout;
using std::endl;
int main()
{
    cout << "2 raised to the power of 10: ";
    cout << 2*2*2*2*2*2*2*2*2*2;
    cout << endl;
    return 0;
}
```