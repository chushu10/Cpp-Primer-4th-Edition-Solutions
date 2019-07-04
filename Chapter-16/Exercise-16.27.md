# Exercise 16.27

Determine which compilation model your compiler uses. Write and call a function template to find the median value in a `vector` that holds objects of unknown type. (Note: The median is a value such that half the elements are larger than the median, and half are smaller.) Structure your program in the normal way: The function definition should go in one file, a declaration for it in a header, which the code that defines and uses the function template should include.

**Answer**:

```cpp
// find_median.h
// header file utlities.h
#ifndef FIND_MEDIAN_H // header gaurd (Section 2.9.2, p. 69)
#define FIND_MEDIAN_H
#include <vector>
template <class T>
typename std::vector<T>::const_iterator find_median(const std::vector<T>&);
#include "find_median.cc" // get the definitions for find_median etc.
#endif

// find_median.cc
#include <vector>

template <class T>
typename std::vector<T>::const_iterator
find_median(const std::vector<T>& vec)
{
    int larger_count = 0;
    int smaller_count = 0;
    typename std::vector<T>::const_iterator cand; // candidate
    typename std::vector<T>::const_iterator iter;

    for (cand = vec.begin(); cand != vec.end(); ++cand) {
        for (iter = vec.begin(); iter != vec.end(); ++iter) {
            if (*cand > *iter) {
                larger_count++;
            } else if (*cand < *iter) {
                smaller_count++;
            }
        }

        if (larger_count == smaller_count) {
            return cand;
        }

        larger_count = 0; // reset for next candidate
        smaller_count = 0;
    }

    return vec.end();
}

// main.cc
#include "find_median.h"
#include <iostream>
#include <vector>
using namespace std;

int main()
{
    vector<int> ivec = {1, 2, 3, 3, 3, 3, 4, 6, 5, 7};
    vector<int>::const_iterator ret = find_median(ivec);
    cout << ( (ret != ivec.end()) ? to_string(*ret) : "No median" ) << endl;
    return 0;
}
```
