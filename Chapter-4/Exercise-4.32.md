# Exercise 4.32

Write a program to initialize a `vector` from an array of `int`s.

**Answer**:

```cpp
#include <vector>
#include <iostream>
using std::vector;
using std::cout;
using std::endl;

int main(int argc, char const *argv[])
{
    int iarr[7] = {0, 1, 2, 3, 4, 5, 6};
    vector<int> ivec(iarr, iarr + 7);
    for (vector<int>::iterator iter = ivec.begin();
                               iter != ivec.end(); ++iter) {
            cout << *iter << " ";
    }
    cout << endl;
    return 0;
}

```