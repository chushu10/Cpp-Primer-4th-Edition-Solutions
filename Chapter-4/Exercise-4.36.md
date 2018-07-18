# Exercise 4.36

Rewrite the program to point the contents of the array `ia` without using a typedef for the type of the pointer in the outer `loop`.

**Answer**:

```cpp
#include <iostream>
using std::cout;
using std::endl;

int main(int argc, char const *argv[])
{
    const size_t rowSize = 3;
    const size_t colSize = 4;
    int ia[rowSize][colSize] = {
        {0, 1, 2, 3},
        {4, 5, 6, 7},
        {8, 9, 10, 11}
    };

    for (int (*p)[colSize] = ia; p != ia + 3; ++p) {
        for (int *q = *p; q != *p + 4; ++q) {
            cout << *q << " "; 
        }
        cout << endl;
    }
    return 0;
}

```