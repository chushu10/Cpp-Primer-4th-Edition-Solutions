# Exercise 14.33

Using the library algorithms and the `GT_cls` class, write a program to find the first element in a sequence that is larger than a specified value.

**Answer**:

```cpp
#include <algorithm>
#include <string>
#include <vector>
#include <iostream>
using namespace std;

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
    vector<string>::size_type wc =
        count_if(words.begin(), words.end(), GT_cls(3));
    cout << wc << endl;
    return 0;
}
```