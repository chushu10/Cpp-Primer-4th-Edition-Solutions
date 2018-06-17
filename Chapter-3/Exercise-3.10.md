# Exercise 3.10

Write a program to strip the punctuation from a     `string`. The input to the program should be a string of characters including punctuation; the output should be a `string` in which the punctuation is removed.

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
    string s;
    cin >> s;
    for (string::size_type ix = 0; ix != s.size(); ++ix) {
        if (!ispunct(s[ix])) {
            cout << s[ix];
        }
    }
    cout << endl;
}
```