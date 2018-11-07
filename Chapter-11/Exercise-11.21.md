# Exercise 11.21

Use `find` to find the last element in a `list` of `int`s with value 0.

**Answer**:

```cpp
#include <list>
#include <algorithm>
#include <iostream>
using namespace std;

int main(int argc, char const *argv[])
{
    list<int> ilist(10, 0);
    list<int>::reverse_iterator it = find(ilist.rbegin(), ilist.rend(), 0);
    cout << *it << endl;
    return 0;
}
```