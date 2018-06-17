# Exercise 3.8

Write a program to read `string`s from the standard input, concatenating what is read into one large `string`. Print the concatenated `string`. Next, change the program to separate adjacent input `string`s by a space.

**Answer**:

```cpp
#include <iostream>
#include <string>
using std::cin;
using std::cout;
using std::endl;
using std::string;
int main()
{
    string s1, s2;
    cin >> s1 >> s2;
    cout << s1 + s2 << endl; // (1) concatenate
    cout << s1 + " " << s2 << endl; // (2) separate by space
    return 0;
}
```