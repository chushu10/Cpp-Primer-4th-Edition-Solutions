# Exercise 11.5

The algorithms library defines a function named `unique_copy` that operates like `unique`, except that it takes a third iterator denoting a sequence into which to copy the unique elements. Write a program that uses `unique_copy` to copy the unique elements from a `list` into an initially empty `vector`.

**Answer**:

```cpp
#include <vector>
#include <list>
#include <algorithm>
#include <iostream>
#include <iterator>
using namespace std;

int main(int argc, char const *argv[])
{
    list<int> ilist;
    ilist.push_back(1);
    ilist.push_back(0);
    ilist.push_back(0);
    ilist.push_back(8);
    ilist.push_back(6);
    vector<int> ivec;

    unique_copy(ilist.begin(), ilist.end(), back_inserter(ivec));
    vector<int>::iterator it = ivec.begin();
    while (it != ivec.end()) {
        cout << *it++ << " ";
    }
    cout << endl;
    return 0;
}
```