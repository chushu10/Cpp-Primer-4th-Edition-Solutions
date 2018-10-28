# Exercise 10.27

Repeat the program from the previous exercise, but this time use `equal_range` to get iterators so that you can erase a range of elements.

**Answer**:

```cpp
#include <iostream>
#include <map>
#include <string>
using namespace std;

int main(int argc, char const *argv[])
{
    multimap<string, string> author_work;
    author_work.insert(make_pair("Cao Xueqing", "Hong Lou Meng"));
    author_work.insert(make_pair("Shi Naian", "San Guo Yan Yi"));
    author_work.insert(make_pair("Shi Naian", "Shui Hu Zhuan"));
    author_work.insert(make_pair("Pu Songling", "Liao Zhai Zhi Yi"));
    author_work.insert(make_pair("Pu Songling", "Liao Zhai"));

    typedef multimap<string, string>::iterator author_it;
    pair<author_it, author_it> range = 
        author_work.equal_range("Pu Songling");
    if (range.first != range.second) {
        author_work.erase(range.first, range.second);
    }

    multimap<string, string>::iterator it = author_work.begin();
    for (; it != author_work.end(); ++it) {
        cout << it->first << ": " << it->second << endl;
    }

    range = author_work.equal_range("Wu Chengen");
    if (range.first != range.second) {
        author_work.erase(range.first, range.second);
    }
    return 0;
}
```