# Exercise 5.21

Write a program to process the elements of a `vector<int>`. Replace each element with an odd value by twice that value.

**Answer**:

```cpp
#include <vector>
#include <iostream>
using std::cin;
using std::cout;
using std::endl;
using std::vector;

int main(int argc, char const *argv[])
{
    vector<int> ivec;
    int input;
    cout << "Input a list of ints(Ctrl + D to end input): ";
    while (cin >> input) {
        ivec.push_back((input % 2 == 0) ? input : 2 * input);
    }
    for (vector<int>::iterator iter = ivec.begin();
                               iter != ivec.end(); ++iter) {
        cout << *iter << " ";
    }
    cout << endl;
    return 0;
}
```