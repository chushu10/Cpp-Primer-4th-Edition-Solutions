# Exercise 4.33

Write a program to copy a `vector` of `int`s into an array of `int`s.

**Answer**:

```cpp
#include <vector>
#include <iostream>
using std::vector;
using std::cin;
using std::cout;
using std::endl;

int main(int argc, char const *argv[])
{
    vector<int> ivec;
    int input;
    size_t num;

    cout << "Input number of ints: ";
    cin >> num;
    
    cout << "Input each int: ";
    for (size_t i = 0; i < num; ++i) {
        cin >> input;
        ivec.push_back(input); 
    }

    int *iarr = new int[num];
    for (size_t i = 0; i < num; ++i) {
        iarr[i] = ivec[i];
        cout << iarr[i] << " ";
    }
    cout << endl;
    delete [] iarr;
    return 0;
}

```