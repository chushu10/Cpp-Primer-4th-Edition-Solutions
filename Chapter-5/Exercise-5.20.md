# Exercise 5.20

Write a program to prompt the user for a pair of numbers and report which is smaller.

**Answer**:

```cpp
#include <iostream>
using std::cin;
using std::cout;
using std::endl;

int main(int argc, char const *argv[])
{
    int a, b;
    cout << "Input two numbers: ";
    cin >> a;
    cin >> b;
    cout << (a < b ? a : b) << " is smaller." << endl; 
    return 0;
}
```