# Exercise 10.26

Write a program that populates a `multimap` of authors and their works. Use `find` to find an element in the `multimap` and erase that element. Be sure your program works correctly if the element you look for is not in the `map`.

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

    multimap<string, string>::iterator iter = 
        author_work.find("Pu Songling");
    if (iter != author_work.end()) {
        author_work.erase(iter);
    }

    multimap<string, string>::iterator it = author_work.begin();
    for (; it != author_work.end(); ++it) {
        cout << it->first << ": " << it->second << endl;
    }

    iter = author_work.find("Wu Chengen");
    if (iter != author_work.end()) {
        author_work.erase(iter);
    }
    return 0;
}
```