# Exercise 3.5

Write a program to read the standard input a line at a time. Modify your program to read a word at a time.

**Answer**:

(1) Read the standard input a line at a time:

```cpp
// main.cpp
#include <iostream>
#include <string>
using std::cin;
using std::cout;
using std::endl;
using std::string;
int main()
{
    string line;
    while (getline(cin, line)) {
        cout << line << endl;
    }
    return 0;
}
```

(2) A word at a time:

```cpp
// main.cpp
#include <iostream>
#include <string>
using std::cin;
using std::cout;
using std::endl;
using std::string;
int main()
{
    string s;
    while (cin >> s) {
        cout << s << endl;
    }
    return 0;
}
```