# Exercise 7.4

Write a program to return the absolute value of its parameter.

**Answer**:

```cpp
#include <iostream>
using std::cout;
using std::endl;

int absolute(int num)
{
    return num > 0 ? num : 0 - num;
}

int main(int argc, char const *argv[])
{
    cout << absolute(-9) << endl;
    return 0;
}

```