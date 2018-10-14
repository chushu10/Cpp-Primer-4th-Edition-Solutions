# Exercise 9.36

Write a program that initializes a `string` from a `vector<char>`.

**Answer**:

```cpp
#include <string>
#include <vector>
#include <iostream>
using namespace std;

int main(int argc, char const *argv[])
{
    vector<char> cvec;
    cvec.push_back('h');
    cvec.push_back('e');
    cvec.push_back('l');
    cvec.push_back('l');
    cvec.push_back('o');
    string s;
    vector<char>::iterator it = cvec.begin();
    for ( ; it != cvec.end(); ++it) {
        s.push_back(*it);
    }
    cout << s << endl;
    return 0;
}
```