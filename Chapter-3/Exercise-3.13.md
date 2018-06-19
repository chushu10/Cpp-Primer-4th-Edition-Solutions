# Exercise 3.13

Read a set of integers into a `vector`. Calculate and print the sum of each pair of adjacent elements in the `vector`. If there is an odd number, tell the user and print the value of the last element without summing it. Now change your program so that it prints the sum of the first and last elements, followed by the sum of the second and second-to-last and so on.

**Answer**:

```cpp
#include <iostream>
#include <vector>
using std::cin;
using std::cout;
using std::endl;
using std::vector;
int main()
{
    int num;
    int elem;
    vector<int> ivec;
    cout << "Please input number of elements of vector:" << endl;
    cin >> num;
    cout << "Please input each element:" << endl;
    for (vector<int>::size_type ix = 0; ix != num; ++ix) {
        cin >> elem;
        ivec.push_back(elem);
    }
    cout << "Now Exercise 3.13 part one:" << endl;
    int last = ivec[0];
    for (vector<int>::size_type ix = 1; ix != ivec.size(); ++ix) {
        if (last % 2 != 0 || ivec[ix] % 2 != 0) {
            cout << "There is an odd number! Print last number " << last << endl;
        } else {
            cout << last + ivec[ix] << endl;
        }
        last = ivec[ix];
    }

    cout << "Now Exercise 3.13 part two:" << endl;
    for (vector<int>::size_type ix = 0; ix != ivec.size() / 2; ++ix) {
        cout << ivec[ix] + ivec[ivec.size() - ix - 1] << endl;
    }
    return 0;
}
```