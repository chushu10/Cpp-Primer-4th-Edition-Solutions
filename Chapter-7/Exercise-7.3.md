# Exercise 7.3

Write a program to take into two `int` parameters and generate the result of raising the first parameter to the power of the second. Write a program to call your function passing it two `int`s. Verify the result.

**Answer**:

```cpp
#include <iostream>
using std::cout;
using std::endl;

int power(int base, int index)
{
    int result = 1;
    for (int i = 0; i < index; ++i) {
        result *= base;
    }
    return result;
}

int main(int argc, char const *argv[])
{
    cout << power(5, 3) << endl;
    return 0;
}
```