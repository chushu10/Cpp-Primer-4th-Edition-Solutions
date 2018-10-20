# Exercise 10.1

Write a program to read a sequence of `string`s and `int`s , storing each into a `pair`. Store the `pair`s in a `vector`.

**Answer**:

```cpp
#include <string>
#include <utility>
#include <iostream>
#include <vector>
using namespace std;

int main(int argc, char const *argv[])
{
    pair<string, int> strIntPair;
    vector< pair<string, int> > pairVec;
    while (cin >> strIntPair.first >> strIntPair.second) {
        pairVec.push_back(strIntPair);
    }
    vector< pair<string, int> >::iterator it = pairVec.begin();
    for (; it != pairVec.end(); ++it) {
        cout << it->first << ": " << it->second << endl;
    }
    return 0;
}
```