# Exercise 10.28

Using the `multimap` from the previous exercise, write a program to generate the list of authors whose name begins with the each letter in the alphabet. Your output should look something like:

```bash
Author Names Beginning with 'A':
Author, book, book, ...
...
Author Names Beginning with 'B':
...
```

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
    author_it it = author_work.begin();
    while (it != author_work.end()) {
        cout << "Author Names Beginning with '" << it->first[0]
             << "':" << endl;
        cout << it->first << ", ";
        pair<author_it, author_it> range = author_work.equal_range(it->first);
        while (range.first != range.second) {
            cout << (range.first)->second << ", ";
            ++range.first;
        }
        cout << endl;
        it = range.first;
    }
    return 0;
}
```