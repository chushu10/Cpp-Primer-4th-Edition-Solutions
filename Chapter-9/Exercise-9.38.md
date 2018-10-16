# Exercise 9.38

Write a program that, given the `string`:

`"ab2c3d7R4E6"`

finds each numeric character and then each alphabetic character. Write two versions of the program. The first should use `find_first_of`, and the second `find_first_not_of`.

**Answer**:

```cpp
#include <string>
#include <iostream>
using namespace std;

int main(int argc, char const *argv[])
{
    string str("ab2c3d7R4E6");
    string numerics("0123456789");
    string::size_type pos = 0;
    // each trip reset pos to the next instance in name
    while ((pos = str.find_first_of(numerics, pos)) != string::npos) {
        cout << "found number at index: " << pos
             << " element is " << str[pos] << endl;
        ++pos; // move to the next character
    }
    pos = 0;
    while ((pos = str.find_first_not_of(numerics, pos)) != string::npos) {
        cout << "found non-number at index: " << pos
             << " element is " << str[pos] << endl;
        ++pos; // move to the next character
    }
    return 0;
}
```
