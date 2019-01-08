# Exercise 14.35

Write a class similar to `GT_cls` , but that tests whether the length of a given string matches its bound. Use that object to rewrite the program in Section 11.2.3 (p. 400 ) to report how many words in the input are of sizes 1 through 10 inclusive.

**Answer**:

```cpp
// ex1434.cc
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

int main(int argc, char const *argv[])
{
    vector<string> words;
    words.push_back("hello");
    words.push_back("world");
    words.push_back("liu");
    words.push_back("chu");
    words.push_back("shu");
    for (size_t i = 0; i != 11; ++i) {
        cout << count_if(words.begin(), words.end(), isOfLength(i))
             << " words " << i
             << " characters" << endl;
    }
    
    return 0;
}
```