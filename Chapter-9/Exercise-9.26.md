# Exercise 9.26

Using the following definition of `ia` , copy `ia` into a `vector` and into a `list`. Use the single iterator form of erase to remove the elements with odd values from your `list` and the even values from your `vector`.

`int ia[] = { 0, 1, 1, 2, 3, 5, 8, 13, 21, 55, 89 };`

**Answer**:

```cpp
#include <iostream>
#include <list>
#include <vector>
using namespace std;

int main(int argc, char const *argv[])
{
    int ia[] = { 0, 1, 1, 2, 3, 5, 8, 13, 21, 55, 89 };
    vector<int> ivec;
    list<int> ilist;

    // copy
    cout << "ia: ";
    size_t size = sizeof(ia) / sizeof(int);
    for (size_t i = 0; i < size; ++i) {
        cout << ia[i] << " ";
        ivec.push_back(ia[i]);
        ilist.push_back(ia[i]);
    }
    cout << endl;

    // erase odd elements from list
    list<int>::iterator it = ilist.begin();
    while (it != ilist.end()) {
        if (*it % 2 != 0) {
            it = ilist.erase(it);
            continue;
        }
        ++it;
    }

    // erase even elements from vector
    vector<int>::iterator it2 = ivec.begin();
    while (it2 != ivec.end()) {
        if (*it2 % 2 == 0) {
            it2 = ivec.erase(it2);
            continue;
        }
        ++it2;
    }

    it = ilist.begin();
    cout << "ilist after erase: ";
    for (; it != ilist.end(); ++it) {
        cout << *it << " ";
    }
    cout << endl;

    it2 = ivec.begin();
    cout << "ivec after erase: ";
    for (; it2 != ivec.end(); ++it2) {
        cout << *it2 << " ";
    }
    cout << endl;

    return 0;
}
```