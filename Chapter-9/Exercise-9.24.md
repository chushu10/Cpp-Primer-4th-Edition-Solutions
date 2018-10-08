# Exercise 9.24

Write a program that fetches the first element in a `vector`. Do so using at, the subscript operator, `front`, and `begin`. Test the program on an empty `vector`.

**Answer**:

```cpp
#include <vector>
using std::vector;

int main(int argc, char const *argv[])
{
    vector<int> ivec;
    // ...
    if (!ivec.empty()) { // ensure that ivec is not empty
        vector<int>::reference ival = ivec.front();
        vector<int>::reference ival2 = *ivec.begin();
        vector<int>::reference ival3 = ivec[0];
        vector<int>::reference ival4 = ivec.at(0);
    }
    return 0;
}
```