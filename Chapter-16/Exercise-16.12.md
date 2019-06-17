# Exercise 16.12

Write a function template that takes a pair of values that represent iterators of unknown type. Find the value that occurs most frequently in the sequence.

**Answer**:

```cpp
#include <iostream>
#include <vector>
using namespace std;

template <typename InputIterator>
InputIterator FindMostFrequentValue(InputIterator first,
                                    InputIterator last)
{
    InputIterator current = first;
    int count = 0, max = 0;
    InputIterator ret;

    while (current != last) {
        for (InputIterator iter = first; iter != last; ++iter) {
            if (*current == *iter) {
                ++count;
            }
        }
        if (count > max) {
            max = count;
            ret = current;
        }
        ++current;
    }
    
    return ret;
}

int main()
{
    static const int arr[] = {16,2,77,88,29,2,88,88};
    vector<int> ivec(arr, arr + sizeof(arr) / sizeof(arr[0]) );
    vector<int>::iterator it = FindMostFrequentValue(ivec.begin(), ivec.end() );
    cout << *it << endl;
    return 0;
}
```
