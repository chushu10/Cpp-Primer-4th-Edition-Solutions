# Exercise 14.36

Revise the previous program to report the count of words that are sizes 1 through 9 and 10 or more.

```cpp
#include <algorithm>
#include <vector>
#include <iostream>
#include <string>
using namespace std;

class isOfLength {
public:
    isOfLength(size_t val = 0): bound(val) { }
    bool operator()(const string &s)
        { return s.size() == bound; }
private:
    string::size_type bound;
};

class GT_cls {
public:
    GT_cls(size_t val = 0): bound(val) { }
    bool operator()(const string &s)
        { return s.size() >= bound; }
private:
    string::size_type bound;
};

int main(int argc, char const *argv[])
{
    vector<string> words;
    words.push_back("hello");
    words.push_back("world");
    words.push_back("liu");
    words.push_back("chu");
    words.push_back("shu");
    words.push_back("this is awesome");
    words.push_back("because of you!");
    for (size_t i = 0; i != 11; ++i) {
        cout << count_if(words.begin(), words.end(), isOfLength(i))
             << " words " << i
             << " characters" << endl;
    }
    cout << count_if(words.begin(), words.end(), GT_cls(10))
         << " words " << 10
         << " characters or longer" << endl;
    return 0;
}
```