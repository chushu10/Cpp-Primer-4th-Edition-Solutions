# Exercise 11.17

Use a pair of `istream_iterators` to initialize a `vector` of `int`s.

**Answer**:

```cpp
#include <vector>
#include <iterator>
#include <iostream>
using namespace std;

int main(int argc, char const *argv[])
{
    istream_iterator<int> input_iter(cin), eof;
    vector<int> ivec(input_iter, eof);
    vector<int>::iterator it = ivec.begin();
    while (it != ivec.end()) {
        cout << *it++ << " ";
    }
    cout << endl;
    return 0;
}
```