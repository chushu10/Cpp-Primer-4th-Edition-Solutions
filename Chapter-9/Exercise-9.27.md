# Exercise 9.27

Write a program to process a `list` of `string`s. Look for a particular value and, if found, remove it. Repeat the program using a `deque`.

**Answer**:

```cpp
#include <deque>
#include <list>
#include <string>
#include <iostream>
using namespace std;

int main(int argc, char const *argv[])
{
    list<string> slist;
    deque<string> sdeque;

    slist.push_back("hello");
    slist.push_back("how");
    slist.push_back("hi");
    slist.push_back("hi");
    slist.push_back("hello");
    slist.push_back("hi");

    sdeque.push_back("hello");
    sdeque.push_back("how");
    sdeque.push_back("hi");
    sdeque.push_back("hi");
    sdeque.push_back("hello");
    sdeque.push_back("hi");

    // list
    list<string>::iterator it = slist.begin();
    while (it != slist.end()) {
        if (*it == "hi") {
            it = slist.erase(it);
            continue;
        }
        ++it;
    }

    it = slist.begin();
    cout << "slist after erase: ";
    for (; it != slist.end(); ++it) {
        cout << *it << " ";
    }
    cout << endl;

    // deque
    deque<string>::iterator it2 = sdeque.begin();
    while (it2 != sdeque.end()) {
        if (*it2 == "hi") {
            it2 = sdeque.erase(it2);
            continue;
        }
        ++it2;
    }

    it2 = sdeque.begin();
    cout << "sdeque after erase: ";
    for (; it2 != sdeque.end(); ++it2) {
        cout << *it2 << " ";
    }
    cout << endl;

    return 0;
}
```