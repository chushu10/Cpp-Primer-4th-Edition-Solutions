# Exercise 4.25

Write a program to compare two `string`s. Now write a program to compare the value of two C-style character strings.

**Answer**:

`string` compare:

```cpp
#include <string>
#include <iostream>
using std::string;
using std::cin;
using std::cout;
using std::endl;
int main(int argc, char const *argv[])
{
    string a;
    string b;
    cout << "Input first string: ";
    cin >> a;
    cout << "Input secend string: ";
    cin >> b;
    if (a == b) {
        cout << "a(" << a << ") and b(" 
             << b << ") are equal" << endl;
    } else {
        cout << "a(" << a << ") and b(" 
             << b << ") are different" << endl;
    }
    return 0;
}

```

C-style null terminated string compare:

```cpp
#include <iostream>
#include <cstring>
using std::cin;
using std::cout;
using std::endl;
int main(int argc, char const *argv[])
{
    const int strSize = 11; // 10 characters plus one null
    char a[strSize];
    char b[strSize];
    cout << "Input first string(10 chars most): ";
    cin >> a;
    cout << "Input secend string(10 chars most): ";
    cin >> b;
    if (strcmp(a, b) == 0) {
        cout << "a(" << a << ") and b(" 
             << b << ") are equal" << endl;
    } else {
        cout << "a(" << a << ") and b(" 
             << b << ") are different" << endl;
    }
    return 0;
}
```

The behavior is undefined if you write more than 10 characters to C-style char array `a` or `b`.