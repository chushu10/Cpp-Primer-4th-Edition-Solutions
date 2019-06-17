# Exercise 16.14

Rewrite the function from the previous exercise to use iterators returned from `begin` and `end` to control the loop.

**Answer**:

```cpp
#include <iostream>
#include <vector>
using namespace std;

template <typename Container>
void PrintElements(Container &container)
{
    typename Container::const_iterator beg = container.begin();
    typename Container::const_iterator end = container.end();

    while (beg != end) {
        cout << *beg++ << " ";
    }
    cout << endl;
}

int main()
{
    static const int arr[] = {16,2,77,88,29,2,88,88};
    vector<int> ivec(arr, arr + sizeof(arr) / sizeof(arr[0]) );
    PrintElements(ivec);
    return 0;
}
```
