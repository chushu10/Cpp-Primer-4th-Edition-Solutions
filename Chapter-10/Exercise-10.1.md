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
    pair<string, int> str_int_pair;
    vector< pair<string, int> > pair_vec;
    while (cin >> str_int_pair.first >> str_int_pair.second) {
        pair_vec.push_back(str_int_pair);
    }
    vector< pair<string, int> >::iterator it = pair_vec.begin();
    for (; it != pair_vec.end(); ++it) {
        cout << it->first << ": " << it->second << endl;
    }
    return 0;
}
```