# Exercise 3.7

Write a program to read two `string`s and report whether the `string`s are equal. If not, report which of the two is the larger. Now, change the program to report whether the `string`s have the same length and if not report which is longer.

**Answer**:

(1) Which one is larger:

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
    string s1, s2;
    cin >> s1 >> s2;
    if (s1 == s2) {
        cout << s1 << " and " << s2 << " are the same" << endl;
    } else if (s1 > s2) {
        cout << s1 << " is larger than " << s2 << endl;
    } else {
        cout << s1 << " is less than " << s2 << endl;
    }
    return 0;
}
```

(2) Which one is longer:

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
    string s1, s2;
    cin >> s1 >> s2;
    if (s1.size() == s2.size()) {
        cout << s1 << " and " << s2 << " are the same length" << endl;
    } else if (s1.size() > s2.size()) {
        cout << s1 << " is longer than " << s2 << endl;
    } else {
        cout << s1 << " is shoter than " << s2 << endl;
    }
    return 0;
}
```