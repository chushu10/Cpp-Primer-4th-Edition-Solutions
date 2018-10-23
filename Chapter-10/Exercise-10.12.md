# Exercise 10.12

Rewrite the word-count program that you wrote in the exercises for Section 10.3.4 (p. 364 ) to use `insert` instead of subscripting. Explain which program you think is easier to write and read. Explain your reasoning.

```cpp
#include <string>
#include <map>
#include <iostream>
using namespace std;

int main(int argc, char const *argv[])
{
    map<string, int> word_count;
    string input;
    while (cin >> input) {
        pair< map<string, int>::iterator, bool> ret = word_count.insert(make_pair(input, 1));
        if (!ret.second) {
            ++ret.first->second;
        }
    }
    map<string, int>::iterator it = word_count.begin();
    for (; it != word_count.end(); ++it) {
        cout << it->first << ": " << it->second << " times" << endl;
    }
    return 0;
}
```

The subscripting version is absolutely easier to write and read. Since you don't have to remember the return value of the `insert` function and its arguments, you are less prone to make compile error. BTW, the subscripting version is also reader friendly.
